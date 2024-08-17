# $OpenBSD$

COMMENT =		LinuxDoc tools

DISTNAME =		linuxdoc-tools-0.9.82
REVISION =		0

CATEGORIES =		textproc

HOMEPAGE =		https://packages.debian.org/sid/linuxdoc-tools

# GPL3+ and Public Domain
PERMIT_PACKAGE =	Yes 

SITES =			${SITE_DEBIAN:=main/l/linuxdoc-tools/}

DISTFILES =		linuxdoc-tools_0.9.82.orig.tar.gz

# Dependencies
#

WANTLIB =		c			

RUN_DEPENDS =		lang/gawk         \
			print/texlive/base\
			textproc/groff    \
			textproc/linuxdoc \
			textproc/opensp

BUILD_DEPENDS =		archivers/gtar \
			${RUN_DEPENDS}

USE_GMAKE =		Yes
CONFIGURE_STYLE =	gnu

.include <bsd.port.mk>
