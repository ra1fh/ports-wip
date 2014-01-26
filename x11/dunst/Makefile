# $OpenBSD$

COMMENT=		customizable and lightweight notification daemon

DISTNAME=		dunst-1.0.0

CATEGORIES=		x11

HOMEPAGE=		http://www.knopwob.org/dunst/

# BSD
PERMIT_PACKAGE_CDROM=	Yes
PERMIT_PACKAGE_FTP=	Yes
PERMIT_DISTFILES_FTP=	Yes

MASTER_SITES=		http://www.knopwob.org/public/dunst-release/
EXTRACT_SUFX=		.tar.bz2

WANTLIB += 		X11 Xext Xft Xinerama Xss c fontconfig freetype m pthread
WANTLIB += 		xdg-basedir z
WANTLIB += 		cairo dbus-1 gio-2.0 glib-2.0 gobject-2.0 intl
WANTLIB += 		pango-1.0 pangocairo-1.0 pangoft2-1.0

LIB_DEPENDS=		x11/libxdg-basedir \
			graphics/cairo \
			x11/dbus \
			devel/pango

USE_GMAKE =		Yes
MAKE_ENV = 		DESTDIR=/

.include <bsd.port.mk>
