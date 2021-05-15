# $OpenBSD$

COMMENT=	Low level tools for Lego Mindstorms NXT

DISTNAME=	libnxt-0.3

CATEGORIES=	devel

HOMEPAGE=	https://code.google.com/archive/p/libnxt/

# GPLv2
PERMIT_PACKAGE=	Yes

MASTER_SITES=	https://libnxt.googlecode.com/files/

MODULES=	devel/scons \
		lang/python

WANTLIB=	c pthread usb

BUILD_DEPENDS=	lang/python/${MODPY_DEFAULT_VERSION_2}
LIB_DEPENDS=	devel/libusb-compat

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/fwexec ${PREFIX}/bin/fwexec
	${INSTALL_PROGRAM} ${WRKSRC}/fwflash ${PREFIX}/bin/fwflash
	${INSTALL_MAN} ${FILESDIR}/fwexec.1 ${PREFIX}/man/man1
	${INSTALL_MAN} ${FILESDIR}/fwflash.1 ${PREFIX}/man/man1
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/libnxt
	${INSTALL_DATA} ${WRKSRC}/README ${PREFIX}/share/doc/libnxt/

.include <bsd.port.mk>
