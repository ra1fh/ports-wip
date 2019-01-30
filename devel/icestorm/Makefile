# $OpenBSD$

COMMENT =	icestorm tools for Lattice iCE40 FPGA

V =		20181231
DISTNAME =	${GH_PROJECT}-${V}
PKGNAME =	icestorm-${V}

GH_ACCOUNT =	cliffordwolf
GH_PROJECT =	icestorm
GH_COMMIT =	c0cbae88ab47a3879aacf80d53b6a85710682a6b


CATEGORIES =	devel

HOMEPAGE =	http://www.clifford.at/icestorm

MAINTAINER =		Ralf Horstmann <ralf-lists@ackstorm.de>

PERMIT_PACKAGE_CDROM =	Yes

WANTLIB =		c

MODULES =		gcc4

USE_GMAKE =		Yes
DESTDIRNAME =		NODESTDIR
MAKE_ENV =		CC=eg++ CXX=eg++

.include <bsd.port.mk>
