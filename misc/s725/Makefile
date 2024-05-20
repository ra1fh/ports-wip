# $OpenBSD$

COMMENT=		Communicate with Polar S725X heart rate monitor

V =			20210228
REVISION =		1
GH_ACCOUNT =		ra1fh
GH_PROJECT =		s725
GH_COMMIT = 		1c66e2e122f16f392358f1a4a61a8e033ace53d1

DISTNAME =		${GH_PROJECT}-${V}

CATEGORIES=		misc

HOMEPAGE=		https://github.com/ra1fh/s725

MAINTAINER=		Ralf Horstmann <ralf+ports@ackstorm.de>

PERMIT_PACKAGE=		Yes

RUN_DEPENDS=		lang/python/3.11 \
			math/py-numpy,python3 \
			graphics/py-matplotlib,python3

WANTLIB += 		c

.include <bsd.port.mk>
