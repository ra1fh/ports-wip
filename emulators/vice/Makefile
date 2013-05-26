# $OpenBSD$

COMMENT=	versatile commodore emulator

DISTNAME=		vice-2.4

CATEGORIES=	emulators

HOMEPAGE=	http://vice-emu.sourceforge.net/

PERMIT_PACKAGE_CDROM=	Yes
PERMIT_PACKAGE_FTP=		Yes
PERMIT_DISTFILES_FTP=	Yes

LIB_DEPENDS  = x11/gtk+2
LIB_DEPENDS += devel/sdl
LIB_DEPENDS += graphics/libungif x11/gtkglext
LIB_DEPENDS += devel/vte
LIB_DEPENDS += audio/lame

WANTLIB += GL X11 Xcomposite Xcursor Xdamage Xext Xfixes Xi Xinerama
WANTLIB += Xrandr Xrender c expat fontconfig freetype m ossaudio
WANTLIB += pcap pixman-1 pthread pthread-stubs readline stdc++
WANTLIB += termcap usbhid xcb xcb-render xcb-shm z
WANTLIB += cairo expat
WANTLIB += fontconfig freetype gdk-x11-2.0 gdk_pixbuf-2.0 gio-2.0 glib-2.0
WANTLIB += gmodule-2.0 gobject-2.0 gtk-x11-2.0
WANTLIB += m pango-1.0 pangocairo-1.0 pangoft2-1.0 pixman-1
WANTLIB += png pthread z pthread-stubs xcb
WANTLIB += xcb-render GL xcb-shm
WANTLIB += atk-1.0 iconv intl
WANTLIB += GLU ICE SM Xmu Xt
WANTLIB += vte

# added for sdlsound
WANTLIB += Xxf86vm jpeg SDL ungif

CONFIGURE_STYLE= simple

CONFIGURE_ARGS += --enable-gnomeui --with-sdlsound --enable-ethernet --disable-ffmpeg
CONFIGURE_ARGS += --mandir=/usr/local/man
MAKE_ENV        = DESTDIR=${PREFIX}

MASTER_SITES =	${MASTER_SITE_SOURCEFORGE:=vice-emu/}


post-install:


.include <bsd.port.mk>
