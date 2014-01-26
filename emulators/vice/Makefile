# $OpenBSD$

COMMENT=		versatile commodore emulator

DISTNAME=		vice-2.4

CATEGORIES=		emulators

HOMEPAGE=		http://vice-emu.sourceforge.net/

PERMIT_PACKAGE_CDROM=	Yes
PERMIT_PACKAGE_FTP=	Yes
PERMIT_DISTFILES_FTP=	Yes

LIB_DEPENDS=		x11/gtk+2 \
			x11/gtkglext \
			devel/sdl \
			devel/vte \
			graphics/libungif \
			audio/lame

WANTLIB =		GL X11 Xcomposite Xcursor Xdamage Xext Xfixes   \
			Xi Xinerama Xrandr Xrender c expat fontconfig	\
			freetype m ossaudio pcap pixman-1 pthread	\
			pthread-stubs readline stdc++ termcap usbhid	\
			xcb xcb-render xcb-shm z cairo expat		\
			fontconfig freetype gdk-x11-2.0			\
			gdk_pixbuf-2.0 gio-2.0 glib-2.0 gmodule-2.0	\
			gobject-2.0 gtk-x11-2.0 m pango-1.0		\
			pangocairo-1.0 pangoft2-1.0 pixman-1 png	\
			pthread z pthread-stubs xcb xcb-render GL	\
			xcb-shm atk-1.0 iconv intl GLU ICE SM Xmu Xt	\
			vte

# added for sdlsound
WANTLIB += 		Xxf86vm jpeg SDL ungif

CONFIGURE_STYLE= 	simple

CONFIGURE_ARGS += 	--enable-gnomeui --with-sdlsound --enable-ethernet --disable-ffmpeg
CONFIGURE_ARGS += 	--mandir=/usr/local/man
MAKE_ENV = 		DESTDIR=${PREFIX}

MASTER_SITES =		${MASTER_SITE_SOURCEFORGE:=vice-emu/}


post-install:


.include <bsd.port.mk>
