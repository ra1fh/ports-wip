# $OpenBSD$

COMMENT =		PICkit 2 Command Line Interface

DISTNAME =		pk2cmdv1.20LinuxMacSource
PKGNAME =    		pk2cmd-1.20
EXTRACT_SUFX = 		.tar.gz
WRKDIST =		${WRKDIR}/pk2cmdv1.20LinuxMacSource

REVISION =		0

CATEGORIES =		devel

HOMEPAGE =		http://www.microchip.com/DevelopmentTools/ProductDetails.aspx?PartNO=pg164120

PERMIT_PACKAGE =	Yes

USE_GMAKE = 		Yes

SITES = 		http://ww1.microchip.com/downloads/en/DeviceDoc/

WANTLIB += 		c m usb
WANTLIB += 		${COMPILER_LIBCXX}

LIB_DEPENDS = 		devel/libusb-compat

do-build:
	cd ${WRKSRC} && $(MAKE_PROGRAM) linux CC=c++ CXX=c++

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/pk2cmd ${PREFIX}/bin/pk2cmd
	${INSTALL_DATA_DIR} ${PREFIX}/share/pk2cmd
	${INSTALL_DATA} ${WRKSRC}/PK2DeviceFile.dat ${PREFIX}/share/pk2cmd

.include <bsd.port.mk>
