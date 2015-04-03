# $OpenBSD$

COMMENT=		cross development package for 6502 systems

V =			20150325
GH_ACCOUNT =		cc65
GH_PROJECT =		cc65
GH_COMMIT = 		c3bec9368b4e78e35fc655ac71a70ddcef747a52

DISTNAME =		${GH_PROJECT}-${V}

CATEGORIES=		devel

HOMEPAGE=		https://cc65.github.io/cc65/

PERMIT_PACKAGE_CDROM=	Yes

WANTLIB += 		c m

BUILD_DEPENDS=		textproc/linuxdoc-tools

USE_GMAKE = 		Yes
ALL_TARGET =		all doc

MAKE_ENV =		prefix=${PREFIX}

.include <bsd.port.mk>
