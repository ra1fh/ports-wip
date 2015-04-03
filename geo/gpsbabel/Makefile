# $OpenBSD: Makefile,v 1.26 2013/10/10 02:08:22 brad Exp $

COMMENT-main=		GPS waypoint, track, and route conversion tool
COMMENT-tk=		Tk front-end to gpsbabel
COMMENT-qt=		Qt front-end to gpsbabel

VERSION=		1.5.2
DISTNAME=		gpsbabel-${VERSION}
PKGNAME-main=		gpsbabel-${VERSION}
PKGNAME-tk=		gpsbabel-tk-${VERSION}
PKGNAME-qt=		gpsbabel-qt-${VERSION}
CATEGORIES=		geo

HOMEPAGE=		http://www.gpsbabel.org/

# GPLv2
PERMIT_PACKAGE_CDROM=	Yes

MASTER_SITES=		http://www.linklevel.net/distfiles/

AUTOCONF_VERSION=	2.61
CONFIGURE_STYLE=	autoconf
CONFIGURE_ARGS+=	--with-zlib=system \
			--with-doc=./babelweb

CONFIGURE_ENV+=		CPPFLAGS="-I${LOCALBASE}/include" \
			LDFLAGS="-L${LOCALBASE}/lib" \
			WEB=${WRKSRC}

MULTI_PACKAGES=		-main -tk -qt

MODULES=		x11/tk x11/qt5

BUILD_DEPENDS=		textproc/libxml \
			textproc/libxslt \
			textproc/fop

LIB_DEPENDS-main=	devel/libusb-compat \
			x11/qt5

cWANTLIB = 		c m pthread
WANTLIB-main += 	usb z estdc++ Qt5Core ${cWANTLIB}
WANTLIB-tk = 
WANTLIB-qt += 		stdc++ ${cWANTLIB} GL
WANTLIB-qt += 		Qt5Core Qt5Gui Qt5Network Qt5WebKit Qt5Xml
WANTLIB-qt += 		Qt5WebKitWidgets Qt5Widgets

LIB_DEPENDS-tk=
PKG_ARCH-tk=	*
RUN_DEPENDS-tk=		geo/gpsbabel \
			${MODTK_RUN_DEPENDS}
RUN_DEPENDS-qt=		geo/gpsbabel \
			devel/desktop-file-utils

pre-configure:
	${SUBST_CMD} ${WRKSRC}/guibabel
	@perl -pi -e 's/gpsbabelfe-bin/guibabel-qt/' \
		${WRKSRC}/gui/gpsbabel.desktop
post-configure:
	cd ${WRKSRC}/gui && ${SETENV} ${CONFIGURE_ENV} qmake-qt5 \
		app.pro
post-build:
	cd ${WRKSRC}/gui && make
	cd ${WRKSRC} && make doc

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/gpsbabel ${PREFIX}/bin
	${INSTALL_PROGRAM} ${WRKSRC}/gui/objects/gpsbabelfe-bin \
		${PREFIX}/bin/guibabel-qt
	${INSTALL_SCRIPT} ${WRKSRC}/guibabel ${PREFIX}/bin
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/gpsbabel
	${INSTALL_DATA} ${WRKSRC}/README* ${PREFIX}/share/doc/gpsbabel
	${INSTALL_DATA} ${WRKSRC}/gpsbabel.pdf ${PREFIX}/share/doc/gpsbabel
	${INSTALL_DATA_DIR} ${PREFIX}/share/applications
	${INSTALL_DATA} ${WRKSRC}/gui/gpsbabel.desktop \
		${PREFIX}/share/applications
	${INSTALL_DATA_DIR} ${PREFIX}/share/pixmaps
	${INSTALL_DATA} ${WRKSRC}/gui/images/appicon.png \
		${PREFIX}/share/pixmaps/gpsbabel.png

.include <bsd.port.mk>
