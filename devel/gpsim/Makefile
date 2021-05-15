# $OpenBSD:$

# XXX building gpsim while a version is already installed
# may cause the build to fail because libraries are linked
# from the installed version

COMMENT =		PIC microcontroller emulator

SVNREV =		2556
PKGNAME =		gpsim-0.31.1.$(SVNREV)
DISTNAME =		gpsim-code-r$(SVNREV)-trunk
EXTRACT_SUFX =		.zip
WRKDIST=		${WRKDIR}/gpsim-code-r$(SVNREV)-trunk

CATEGORIES =		devel

HOMEPAGE =		http://gpsim.sourceforge.net

MASTER_SITES =		https://sourceforge.net/code-snapshots/svn/g/gp/gpsim/code/

MAINTAINER =		Ralf Horstmann <ralf+ports@ackstorm.de>

# GPLv2+ LGPLv2+
PERMIT_PACKAGE =	Yes

SHARED_LIBS +=  gpsim                     0.0 # 0.0
SHARED_LIBS +=  gpsim_dspic               0.0 # 0.0
SHARED_LIBS +=  gpsim_eXdbm               0.0 # 0.0
SHARED_LIBS +=  gpsim_modules             0.0 # 0.0
SHARED_LIBS +=  gpsimcli                  0.0 # 0.0
SHARED_LIBS +=  gpsimgui                  0.0 # 0.0
SHARED_LIBS +=  gpsim_extras              0.0 # 0.0

WANTLIB = c m readline z
WANTLIB += X11 Xcomposite Xcursor Xdamage Xext Xfixes Xi Xinerama
WANTLIB += Xrandr Xrender atk-1.0 cairo expat ffi fontconfig freetype
WANTLIB += gdk-x11-2.0 gtk-x11-2.0 iconv
WANTLIB += intl pcre pixman-1 png popt pthread
WANTLIB += xcb xcb-render xcb-shm gmodule-2.0 graphite2
WANTLIB += gdk_pixbuf-2.0 gio-2.0 glib-2.0 gobject-2.0 gthread-2.0
WANTLIB += pango-1.0 pangocairo-1.0 pangoft2-1.0 harfbuzz
WANTLIB += ${COMPILER_LIBCXX} curses fribidi

BUILD_DEPENDS =		devel/bison \
			print/lyx

LIB_DEPENDS =		x11/gtk+2 \
			devel/popt

CONFIGURE_STYLE =	autoreconf
CONFIGURE_ENV =		CPPFLAGS="-I${LOCALBASE}/include" \
			CFLAGS="-L${LOCALBASE}/lib" \
			YACC=bison

AUTORECONF =		sh ./autogen.sh
AUTOCONF_VERSION =	2.69
AUTOMAKE_VERSION =	1.16

post-install:
	rm ${PREFIX}/lib/libgpsim*.la
	rm ${PREFIX}/lib/libgpsim*.a

.include <bsd.port.mk>
