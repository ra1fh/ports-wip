# $OpenBSD$

COMMENT =		TI's open source compiler for MSP430 microcontrollers#'

V =			4_00_01_00
PKGNAME =		ti-msp430gcc-${V:S/_/./g}
GCC_V =			5.3.0
CATEGORIES =		devel

HOMEPAGE =		http://www.ti.com/tool/msp430-gcc-opensource

# GPLv2+BSD
PERMIT_PACKAGE =	Yes

MASTER_SITES =		http://software-dl.ti.com/msp430/msp430_public_sw/mcu/msp430/MSPGCC/$V/exports/
DIST_SUBDIR =		ti-msp430gcc-$V
DISTFILES =		msp430-gcc-source.tar.bz2 \
			msp430-gcc-support-files.zip

MODULES = 		gcc4
MODGCC4_ARCHS=		*
MODGCC4_LANGS=		c c++

WANTLIB += c gmp m mpc mpfr ${COMPILER_LIBCXX} z

BUILD_DEPENDS =		archivers/bzip2 \
			archivers/unzip \
			devel/autogen
BUILD_DEPENDS +=	sysutils/coreutils # autoconf picks up gmkdir
LIB_DEPENDS =		devel/libmpc

CONFIGURE_STYLE =	gnu
CONFIGURE_ARGS =	--target=msp430-none-elf \
			--program-prefix=msp430-elf- \
			--enable-languages=c \
			--disable-nls \
			--with-mpc=${LOCALBASE} \
			--with-mpfr=${LOCALBASE} \
			--with-gmp=${LOCALBASE} \
			--disable-lto
# Prevents building gdbtk, and a whole bunch of patching
CONFIGURE_ARGS +=	--without-x
CONFIGURE_ARGS +=	--datarootdir=${LOCALBASE}/msp430-none-elf
CONFIGURE_ARGS +=	--includedir=${LOCALBASE}/msp430-none-elf/include
CONFIGURE_ENV =		TARGET=msp430-none-elf

USE_GMAKE =		Yes
SEPARATE_BUILD =	Yes

SUBST_VARS +=		DESTDIR GCC_V

WRKSRC =		${WRKDIR}/sources/tools

post-extract:
.for c in dejagnu intl itcl tcl tk
	rm -r ${WRKSRC}/$c
.endfor

post-patch:
	cd ${WRKSRC} && autogen Makefile.def

pre-configure:
	${SUBST_CMD} ${WRKSRC}/libgloss/msp430/Makefile.in

post-install:
	rm ${PREFIX}/info/*
	${INSTALL_SCRIPT} ${WRKDIR}/GCC_RH/include/*.ld \
		${PREFIX}/msp430-none-elf/lib
	${INSTALL_DATA} ${WRKDIR}/GCC_RH/include/*.h \
		${PREFIX}/msp430-none-elf/include

.include <bsd.port.mk>
