# $OpenBSD: $

ONLY_FOR_ARCHS =	amd64 i386

COMMENT =		cycling performance software

DISTNAME =		GoldenCheetah-3.6-2101

CATEGORIES =		misc

HOMEPAGE =		http://www.goldencheetah.org

MAINTAINER =		David Schaefer <dawedawe@gmx.de>

# GPLv2
PERMIT_PACKAGE =	Yes

WANTLIB +=		c GL m pthread z usb
WANTLIB += 		Qt5Concurrent Qt5Core Qt5Gui Qt5Multimedia
WANTLIB += 		Qt5MultimediaWidgets Qt5Network Qt5SerialPort Qt5Sql
WANTLIB += 		Qt5Svg Qt5WebKit Qt5WebKitWidgets Qt5Widgets Qt5Xml
WANTLIB += 		crypto ssl

GH_ACCOUNT =		GoldenCheetah
GH_PROJECT =		GoldenCheetah
GH_TAGNAME =		v3.6-DEV2101

MODULES =		x11/qt5
BUILD_DEPENDS =		devel/bison

LIB_DEPENDS +=		devel/libusb-compat

PARALLEL_BUILD =	No
USE_GMAKE =		Yes

pre-patch:
	@cp ${WRKSRC}/src/gcconfig.pri.in ${WRKSRC}/src/gcconfig.pri
	@cp ${WRKSRC}/qwt/qwtconfig.pri.in ${WRKSRC}/qwt/qwtconfig.pri

pre-build:
	@cd ${WRKSRC} && ${LOCALBASE}/bin/qmake-qt5 -recursive

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/src/GoldenCheetah ${PREFIX}/bin

.include <bsd.port.mk>
