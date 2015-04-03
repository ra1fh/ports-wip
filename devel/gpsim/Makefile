# $OpenBSD:$

SHARED_ONLY =		Yes

COMMENT =		PIC microcontroller emulator
DISTNAME =		gpsim-0.28.1
PKGNAME =		gpsim-0.28.1

CATEGORIES =		devel

HOMEPAGE =		http://gpsim.sourceforge.net

MAINTAINER =		Ralf Horstmann <ralf-lists@ackstorm.de>

# GPLv2+ LGPLv2+
PERMIT_PACKAGE_CDROM =	Yes
PERMIT_PACKAGE_FTP =	Yes
PERMIT_DISTFILES_FTP =	Yes

SHARED_LIBS +=  gpsim                     0.0 # 0.0
SHARED_LIBS +=  gpsim_ds1307              0.0 # 0.0
SHARED_LIBS +=  gpsim_dspic               0.0 # 0.0
SHARED_LIBS +=  gpsim_eXdbm               0.0 # 0.0
SHARED_LIBS +=  gpsim_graphicLCD          0.0 # 0.0
SHARED_LIBS +=  gpsim_lcd                 0.0 # 0.0
SHARED_LIBS +=  gpsim_modules             0.0 # 0.0
SHARED_LIBS +=  gpsimcli                  0.0 # 0.0
SHARED_LIBS +=  gpsimgui                  0.0 # 0.0
SHARED_LIBS +=  gpsim_dht11               0.0 # 0.0
SHARED_LIBS +=  gpsim_ds1820              0.0 # 0.0

WANTLIB = c m readline stdc++ termcap z
WANTLIB += X11 Xcomposite Xcursor Xdamage Xext Xfixes Xi Xinerama
WANTLIB += Xrandr Xrender atk-1.0 cairo expat ffi fontconfig freetype
WANTLIB += gdk-x11-2.0 gtk-x11-2.0 gtkextra-x11-3.0 iconv 
WANTLIB += intl pcre pixman-1 png popt pthread pthread-stubs
WANTLIB += xcb xcb-render xcb-shm gmodule-2.0 graphite2
WANTLIB += gdk_pixbuf-2.0 gio-2.0 glib-2.0 gobject-2.0 gthread-2.0
WANTLIB += pango-1.0 pangocairo-1.0 pangoft2-1.0 harfbuzz

MASTER_SITES =		${MASTER_SITE_SOURCEFORGE:=gpsim/}

BUILD_DEPENDS =		devel/libtool

LIB_DEPENDS =		x11/gtk+2 \
			x11/gtkextra \
			devel/popt

CONFIGURE_STYLE =	gnu
CONFIGURE_ENV =		CPPFLAGS="-I/usr/local/include" CFLAGS="-L/usr/local/lib"
USE_LIBTOOL=		gnu

AUTOCONF_VERSION =	2.67
AUTOMAKE_VERSION =	1.11

post-install:
	rm ${PREFIX}/lib/libgpsim*.la
	rm ${PREFIX}/lib/libgpsim*.a

.include <bsd.port.mk>

