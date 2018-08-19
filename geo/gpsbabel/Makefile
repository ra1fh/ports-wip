# $OpenBSD$

COMMENT=		GPS waypoint, track, and route conversion tool

GH_ACCOUNT=		gpsbabel
GH_PROJECT=		gpsbabel
GH_COMMIT=		54c0ff6ae82ea75e132742b2fe4d179f621ee730

VERSION=		1.5.4
DISTNAME=		gpsbabel-${VERSION}
PKGNAME=		gpsbabel-${VERSION}
CATEGORIES=		geo

HOMEPAGE=		http://www.gpsbabel.org/

# GPLv2
PERMIT_PACKAGE_CDROM=	Yes


AUTOCONF_VERSION=	2.61
CONFIGURE_STYLE=	autoconf
CONFIGURE_ARGS+=	--with-zlib=included \
			--with-doc=./babelweb

CONFIGURE_ENV+=		CPPFLAGS="-I${LOCALBASE}/include" \
			LDFLAGS="-L${LOCALBASE}/lib" \
			WEB=${WRKSRC}

MODULES=		x11/qt5

BUILD_DEPENDS=		textproc/libxml \
			textproc/libxslt \
			textproc/fop

LIB_DEPENDS=		devel/libusb-compat

WANTLIB = 		c m pthread
WANTLIB += 		Qt5Core usb
WANTLIB += 		${COMPILER_LIBCXX}

USE_GMAKE=		Yes

pre-configure:
	${SUBST_CMD} ${WRKSRC}/guibabel
	@perl -pi -e 's/gpsbabelfe-bin/guibabel-qt/' \
		${WRKSRC}/gui/gpsbabel.desktop
post-build:
	cd ${WRKSRC} && JAVA_HOME=/usr/local/jdk-1.8.0 ${MAKE_PROGRAM} doc
	cd ${WRKSRC} && ${MAKE_PROGRAM} check

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/gpsbabel ${PREFIX}/bin
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/gpsbabel
	${INSTALL_DATA} ${WRKSRC}/README* ${PREFIX}/share/doc/gpsbabel
	${INSTALL_DATA} ${WRKSRC}/gpsbabel.pdf ${PREFIX}/share/doc/gpsbabel

.include <bsd.port.mk>
