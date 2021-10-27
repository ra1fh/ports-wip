# $OpenBSD$

COMMENT=	icestorm tools for Lattice iCE40 FPGA

V=		20210906
DISTNAME=	${GH_PROJECT}-${V}
PKGNAME=	icestorm-${V}

GH_ACCOUNT=	YosysHQ
GH_PROJECT=	icestorm
GH_COMMIT=	83b8ef947f77723f602b706eac16281e37de278c


CATEGORIES=	devel

HOMEPAGE=	http://www.clifford.at/icestorm

MAINTAINER=	Ralf Horstmann <ralf+ports@ackstorm.de>

PERMIT_PACKAGE=	Yes

WANTLIB=	c

USE_GMAKE=	Yes
DESTDIRNAME=	NODESTDIR
MAKE_ENV=	CC=cc CXX=c++

.include <bsd.port.mk>
