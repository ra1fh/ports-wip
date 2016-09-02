# $OpenBSD$

COMMENT =		prometheus node_exporter
DISTNAME =		node_exporter-0.12.0

CATEGORIES =		sysutils

HOMEPAGE =		http://prometheus.io/

MAINTAINER =		Ralf Horstmann <ralf-lists@ackstorm.de>

PERMIT_PACKAGE_CDROM =	Yes

WANTLIB =		c pthread

USE_GMAKE = 		Yes

GH_ACCOUNT =		prometheus
GH_PROJECT =		node_exporter
GH_TAGNAME =		0.12.0
#GH_COMMIT =		85100767f75a5866527150fae271e9a3c8ea66a8

MODULES=		lang/go

do-build:
	cd ${WRKSRC} && GOPATH=${MODGO_WORKSPACE} ${MAKE_PROGRAM} build

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/node_exporter ${PREFIX}/bin

.include <bsd.port.mk>
