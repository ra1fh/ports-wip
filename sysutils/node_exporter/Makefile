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
#GH_COMMIT =		1549f3087d5cf7ddff2752d9498fce1a1c4259af

MODULES=		lang/go

do-build:
	cd ${WRKSRC} && ${MODGO_ENV} go get -d
	cd ${WRKSRC} && ${MODGO_ENV} go build

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/node_exporter ${PREFIX}/bin
	${INSTALL_DATA_DIR} ${WRKINST}/${SYSCONFDIR}/rc.d
	${INSTALL_DATA} ${PKGDIR}/nodeexporter.rc ${WRKINST}/${SYSCONFDIR}/rc.d/nodeexporter

.include <bsd.port.mk>
