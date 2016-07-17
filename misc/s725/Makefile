# $OpenBSD$

COMMENT=		Communicate with Polar S725X heart rate monitor

V =			20160717
GH_ACCOUNT =		ra1fh
GH_PROJECT =		s725
GH_COMMIT = 		35fe2c42be7997cf7e2e4cbb80a8ce8332fd0509

DISTNAME =		${GH_PROJECT}-${V}

CATEGORIES=		misc

HOMEPAGE=		https://github.com/ra1fh/s725

MAINTAINER=		Ralf Horstmann <ralf@ackstorm.de>

PERMIT_PACKAGE_CDROM=	Yes

RUN_DEPENDS=		lang/python/3.4 \
			math/py-numpy,python3 \
			graphics/py-matplotlib,python3

WANTLIB += 		c

.include <bsd.port.mk>
