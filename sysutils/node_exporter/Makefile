# $OpenBSD$

COMMENT =	prometheus node_exporter

V =		0.17.0
DISTNAME =	node_exporter-${V}
GH_ACCOUNT =	prometheus
GH_PROJECT =	node_exporter
GH_TAGNAME =	v${V}

CATEGORIES =	sysutils
HOMEPAGE =	http://prometheus.io/

MAINTAINER =	Ralf Horstmann <ralf-lists@ackstorm.de>

# Apache 2.0
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB =	c pthread

SUBST_CARS +=	LOCALBASE

MODULES =	lang/go

do-build:
	cd ${WRKSRC} && ${MODGO_CMD} build -tags nosystemd

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/node_exporter ${PREFIX}/bin
	${INSTALL_DATA_DIR} ${PREFIX}/share/examples/node_exporter/
	${INSTALL_DATA} ${WRKSRC}/text_collector_examples/* \
		${PREFIX}/share/examples/node_exporter/



.include <bsd.port.mk>
