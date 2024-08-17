# $OpenBSD$

COMMENT =		TI open source compiler for MSP430 microcontrollers

V =			9_3_1_2
GCC_V =			9.3.1.11
SUP_V =			1.212
PKGNAME =		ti-msp430gcc-${V:S/_/./g}
DISTNAME = 		msp430-gcc-${GCC_V}-source-full
CATEGORIES =		devel

HOMEPAGE =		http://www.ti.com/tool/msp430-gcc-opensource

# GPLv2+BSD
PERMIT_PACKAGE =	Yes
SITES =			http://software-dl.ti.com/msp430/msp430_public_sw/mcu/msp430/MSPGCC/${V}/export/
DIST_SUBDIR =		ti-msp430gcc-${V}
DISTFILES =		msp430-gcc-${GCC_V}-source-full.tar.bz2 \
			msp430-gcc-support-files-${SUP_V}.zip

WANTLIB += c curses expat m ${COMPILER_LIBCXX}

BUILD_DEPENDS =		archivers/unzip \
			devel/autogen

SHARED_LIBS +=  cc1plugin                 0.0 # 0.0
SHARED_LIBS +=  cp1plugin                 0.0 # 0.0
SHARED_LIBS +=  cc1                       0.0 # 0.0
SHARED_LIBS +=  lto_plugin                0.0 # 0.0

USE_GMAKE =		Yes

CONFIGURE_COMMON = 	--target=msp430-elf \
			--program-prefix=msp430-elf- \
			--enable-languages=c \
			--disable-nls \
			--enable-initfini-array \
			--disable-lto

CONFIGURE_BINUTILS = 	--disable-sim \
			--disable-gdb \
			--disable-werror

CONFIGURE_GCC =		--enable-target-optspace \
			--enable-newlib-nano-formatted-io

CONFIGURE_GDB =		--disable-binutils\
			--disable-gas \
			--disable-ld \
			--disable-gprof \
			--disable-etc \
			--without-mpfr \
			--without-lzma \
			--with-static-standard-libraries \
			--disable-source-highlight \
			--with-python=no

#
# binutils does not build well with clang and mspgcc only builds
# without errors with clang, so use a mixture here
#
MSPGCC = 	egcc
MSPGCXX =	eg++
MSPCC = 	cc
MSPCXX = 	c++

do-configure:
	cd ${WRKSRC}/gcc && /bin/sh contrib/download_prerequisites
	cd ${WRKSRC}/gcc && for dir in libgloss newlib; do \
		ln -fns ../newlib/$$dir $$dir; \
	done

do-build:
	mkdir -p ${WRKSRC}/build/binutils
	cd ${WRKSRC}/build/binutils && \
	CC=${MSPGCC} CXX=${MSPGCXX} ../../binutils/configure ${CONFIGURE_COMMON} ${CONFIGURE_BINUTILS} && \
	CC=${MSPGCC} CXX=${MSPGCXX} gmake && \
	CC=${MSPGCC} CXX=${MSPGCXX} gmake install DESTDIR=${DESTDIR}

	mkdir -p ${WRKSRC}/build/gcc
	cd ${WRKSRC}/build/gcc && \
	(	export PATH=${DESTDIR}/usr/local/bin:$$PATH; \
		CC=${MSPCC} CXX=${MSPCXX} ../../gcc/configure ${CONFIGURE_COMMON} ${CONFIGURE_GCC} && \
		CC=${MSPCC} CXX=${MSPCXX} gmake && \
		CC=${MSPCC} CXX=${MSPCXX} gmake install DESTDIR=${DESTDIR} )

	#mkdir -p ${WRKSRC}/build/gdb
	#cd ${WRKSRC}/build/gdb && \
	#CC=${MSPCC} CXX=${MSPCXX} ../../gdb/configure ${CONFIGURE_COMMON} ${CONFIGURE_GCC} && \
	#CC=${MSPCC} CXX=${MSPCXX} gmake && \
	#CC=${MSPCC} CXX=${MSPCXX} gmake install DESTDIR=${DESTDIR}

do-install:
	mv ${DESTDIR}/usr/local/share/man/man1/* ${DESTDIR}/usr/local/man/man1/ ||:
	mv ${DESTDIR}/usr/local/share/man/man5/* ${DESTDIR}/usr/local/man/man5/ ||:
	rm -rf ${DESTDIR}/usr/local/share/info
	rm -rf ${DESTDIR}/usr/local/share/gdb
	rm -rf ${DESTDIR}/usr/local/share/man
	rm -rf ${DESTDIR}/usr/local/lib/charset.alias
	rm -rf ${DESTDIR}/usr/local/lib/libcc1.*
	rm -rf ${DESTDIR}/usr/local/include

	mkdir -p ${DESTDIR}/usr/local/msp430-elf/include/
	cp ${WRKDIR}/msp430-gcc-support-files/include/*.h ${DESTDIR}/usr/local/msp430-elf/include/
	cp ${WRKDIR}/msp430-gcc-support-files/include/*.csv ${DESTDIR}/usr/local/msp430-elf/include/
	mkdir -p ${DESTDIR}/usr/local/msp430-elf/lib
	cp ${WRKDIR}/msp430-gcc-support-files/include/*.ld ${DESTDIR}/usr/local/msp430-elf/lib/

.include <bsd.port.mk>
