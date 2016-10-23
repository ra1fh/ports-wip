# $OpenBSD: $

ONLY_FOR_ARCHS =	amd64 i386

COMMENT =		cycling performance software

DISTNAME =		GoldenCheetah-3.1

CATEGORIES =		misc

HOMEPAGE =		http://www.goldencheetah.org

MAINTAINER =		David Schaefer <dawedawe@gmx.de>

# GPLv2
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB +=		ICE SM X11 Xext Xi Xinerama Xrender c fontconfig freetype
WANTLIB += 		m pthread stdc++ z
WANTLIB +=		lib/qt4/QtCore lib/qt4/QtGui lib/qt4/QtNetwork lib/qt4/QtScript
WANTLIB +=		lib/qt4/QtSql lib/qt4/QtSvg lib/qt4/QtWebKit lib/qt4/QtXml
WANTLIB +=		clucene-core clucene-shared usb

GH_ACCOUNT =		GoldenCheetah
GH_PROJECT =		GoldenCheetah
GH_TAGNAME =		v3.1
GH_COMMIT =		cc215a1e5cd96d3ea34b74b10512ed35c04ac0a6

MODULES =		x11/qt4
BUILD_DEPENDS =		devel/bison

LIB_DEPENDS +=		devel/libusb-compat \
			textproc/clucene>=2.3

USE_GMAKE =		Yes

pre-patch:
	@cp ${WRKSRC}/src/gcconfig.pri.in ${WRKSRC}/src/gcconfig.pri
	@cp ${WRKSRC}/qwt/qwtconfig.pri.in ${WRKSRC}/qwt/qwtconfig.pri

pre-build:
	@cd ${WRKSRC} && ${LOCALBASE}/bin/qmake4 build.pro

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/src/GoldenCheetah ${PREFIX}/bin

.include <bsd.port.mk>
