# $OpenBSD$

COMMENT =	icestorm tools for Lattice iCE40 FPGA

V =		20161003
DISTNAME =	${GH_PROJECT}-${V}
PKGNAME =	icestorm

GH_ACCOUNT =	cliffordwolf
GH_PROJECT =	icestorm
#GH_TAGNAME =	1.0
GH_COMMIT =	75fd59c5b4d0d11d18af4779d43e155f498268e7


CATEGORIES =	devel

HOMEPAGE =	http://www.clifford.at/icestorm

MAINTAINER =		Ralf Horstmann <ralf@ackstorm.de

PERMIT_PACKAGE_CDROM =	Yes

WANTLIB =		c

# Dependencies
#
MODULES =		gcc4
#BUILD_DEPENDS =	???
#RUN_DEPENDS =		???
#LIB_DEPENDS =		???
#TEST_DEPENDS =		???

#MAKE_FLAGS =		???
#MAKE_ENV =		???
#FAKE_FLAGS =		???
#TEST_FLAGS =		???

USE_GMAKE =		Yes
DESTDIRNAME =		NODESTDIR
MAKE_ENV =		CC=eg++ CXX=eg++

.include <bsd.port.mk>
