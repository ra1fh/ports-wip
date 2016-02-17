# $OpenBSD$

COMMENT =		versatile Commodore emulator

DISTNAME =		vice-2.4.25

CATEGORIES =		emulators

HOMEPAGE =		http://vice-emu.sourceforge.net/

# GPLv2+
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB += ICE SDL SM X11 Xext Xmu Xrandr Xt Xxf86vm
WANTLIB += c jpeg png m pthread readline stdc++ termcap usbhid
WANTLIB += z gif
WANTLIB += GL GLU Xcomposite Xcursor Xdamage Xfixes Xi Xinerama
WANTLIB += Xrender cairo fontconfig freetype gdk-x11-2.0 gdk_pixbuf-2.0
WANTLIB += gio-2.0 glib-2.0 gmodule-2.0 gobject-2.0 gtk-x11-2.0
WANTLIB += intl pango-1.0 pangocairo-1.0 pangoft2-1.0 pcap
WANTLIB += pcap

MASTER_SITES =		${MASTER_SITE_SOURCEFORGE:=vice-emu/}

LIB_DEPENDS =		devel/sdl \
			graphics/giflib \
			graphics/jpeg \
			graphics/png \
			x11/gtk+2

# required to not get --disable-gtk-doc into CONFIGURE_ARGS, which breaks configure
BUILD_DEPENDS =		textproc/gtk-doc

CONFIGURE_STYLE =	gnu autoconf

AUTOCONF_VERSION =	2.68

CONFIGURE_ARGS +=	--without-oss \
			--without-pulse \
			--with-sdlsound \
			--without-xaw3d \
			--enable-gnomeui \
			--enable-ethernet \
			--enable-parsid \
			--disable-realdevice

FONTDIR =	${PREFIX}/share/fonts/vice

pre-configure:
	${SUBST_CMD} ${WRKSRC}/man/vice.1

post-install:
	${INSTALL_DATA_DIR} ${FONTDIR}
	mv ${PREFIX}/lib/vice/fonts/* ${FONTDIR}
	rmdir ${PREFIX}/lib/vice/fonts/

.include <bsd.port.mk>
