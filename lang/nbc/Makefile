# $OpenBSD$

ONLY_FOR_ARCHS =	amd64 i386
# see fpc

COMMENT=		C-like compiler for Lego Mindstorms NXT

DISTNAME=		nbc-1.2.1.r4

CATEGORIES=		lang

HOMEPAGE=		http://bricxcc.sourceforge.net/nbc/

# MPL - Mozilla Public License
PERMIT_PACKAGE_CDROM=	Yes
PERMIT_PACKAGE_FTP=	Yes
PERMIT_DISTFILES_FTP=	Yes

WANTLIB=		c usb 

MASTER_SITES=		${MASTER_SITE_SOURCEFORGE:=bricxcc/NBC_NXC/}
EXTRACT_SUFX= 		.src.tgz

BUILD_DEPENDS=		lang/fpc
LIB_DEPENDS=		devel/libusb-compat

USE_GMAKE= 		Yes

do-extract:
	cd ${WRKDIR}; \
	mkdir nbc-1.2.1.r4; cd nbc-1.2.1.r4; \
	${GZIP_CMD} -dc ${FULLDISTDIR}/${DISTNAME}${EXTRACT_SUFX} | ${TAR} xf -;

do-build:
	cd ${WRKSRC}/NXT && $(MAKE_PROGRAM) -f nbcunix.mak

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/NXT/nbc ${PREFIX}/bin/nbc
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/nbc
	${INSTALL_DATA} ${WRKSRC}/doc/* ${PREFIX}/share/doc/nbc

.include <bsd.port.mk>
