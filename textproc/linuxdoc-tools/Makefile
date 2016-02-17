# $OpenBSD$

COMMENT =		LinuxDoc tools

DISTNAME =		linuxdoc-tools-0.9.69

CATEGORIES =		textproc

HOMEPAGE =		https://packages.debian.org/sid/linuxdoc-tools

# GPL3+ and Public Domain
PERMIT_PACKAGE_CDROM =	Yes 
PERMIT_PACKAGE_FTP =	Yes 
PERMIT_DISTFILES_FTP =	Yes 

MASTER_SITES =		${MASTER_SITE_DEBIAN:=main/l/linuxdoc-tools/}

DISTFILES =		linuxdoc-tools_0.9.69.orig.tar.gz

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
