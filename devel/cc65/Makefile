# $OpenBSD$

COMMENT=		cross development package for 6502 systems

V =			20150801
GH_ACCOUNT =		cc65
GH_PROJECT =		cc65
GH_COMMIT = 		6f24c07836119ef659c95cdb7ced621aa4c3bf88

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
