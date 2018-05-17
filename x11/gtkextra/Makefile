# $OpenBSD$

COMMENT=		extra widgets for GTK+

V=			3.3.4
DISTNAME=		gtkextra-${V}
PKGNAME=		gtkextra-${V}

CATEGORIES=		x11 devel

HOMEPAGE=		http://gtkextra.sourceforge.net

# LGPLv2
PERMIT_PACKAGE_CDROM=	Yes

SHARED_LIBS +=  	gtkextra-x11-3.0          1.0

WANTLIB += 		X11 Xcomposite Xcursor Xdamage Xext Xfixes Xi	\
			Xinerama Xrandr Xrender expat fontconfig	\
			freetype m pixman-1 pthread xcb			\
			xcb-render xcb-shm z cairo ffi gio-2.0		\
			glib-2.0 gmodule-2.0 gobject-2.0 gthread-2.0	\
			iconv intl pcre png pango-1.0 pangocairo-1.0	\
			pangoft2-1.0 harfbuzz graphite2 atk-1.0		\
			gdk-x11-2.0 gdk_pixbuf-2.0 gtk-x11-2.0          \
			fribidi

MASTER_SITES=		${MASTER_SITE_SOURCEFORGE:=gtkextra/}

LIB_DEPENDS=		devel/pango \
			x11/gtk+2 \
			graphics/cairo

USE_GMAKE=		Yes
USE_LIBTOOL=		Yes

CONFIGURE_STYLE= 	gnu
CONFIGURE_ENV=		CPPFLAGS="-I${LOCALBASE}/include" \
			LDFLAGS="-L${LOCALBASE}/lib"

.include <bsd.port.mk>
