# $OpenBSD$

COMMENT=		cross development package for 6502 systems

V =			20160410
GH_ACCOUNT =		cc65
GH_PROJECT =		cc65
GH_COMMIT = 		e809d6bf0d0ed35bee291cffb845b280e42a9bc6

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
