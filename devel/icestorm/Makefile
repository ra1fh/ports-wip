# $OpenBSD$

COMMENT=	icestorm tools for Lattice iCE40 FPGA

V=		20210309
DISTNAME=	${GH_PROJECT}-${V}
PKGNAME=	icestorm-${V}

GH_ACCOUNT=	YosysHQ
GH_PROJECT=	icestorm
GH_COMMIT=	c495861c19bd0976c88d4964f912abe76f3901c3


CATEGORIES=	devel

HOMEPAGE=	http://www.clifford.at/icestorm

MAINTAINER=	Ralf Horstmann <ralf+ports@ackstorm.de>

PERMIT_PACKAGE=	Yes

WANTLIB=	c

MODULES=	gcc4

USE_GMAKE=	Yes
DESTDIRNAME=	NODESTDIR
MAKE_ENV=	CC=eg++ CXX=eg++

.include <bsd.port.mk>
