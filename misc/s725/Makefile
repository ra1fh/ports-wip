# $OpenBSD$

COMMENT=		Communicate with Polar S725X heart rate monitor

V =			20240520
GH_ACCOUNT =		ra1fh
GH_PROJECT =		s725
GH_COMMIT = 		34fc2b8d3291e6c4507c08570eca056ccdee40ff

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
