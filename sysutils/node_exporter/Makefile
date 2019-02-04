# $OpenBSD$

COMMENT =	prometheus node_exporter

VERSION =	0.17.0
DISTNAME =	node_exporter-${VERSION}
CATEGORIES =	sysutils
GH_ACCOUNT =	prometheus
GH_PROJECT =	node_exporter
GH_TAGNAME =	v${VERSION}

HOMEPAGE =	https://github.com/prometheus/node_exporter

MAINTAINER =	Ralf Horstmann <ralf+ports@ackstorm.de>

# Apache 2.0
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB =	c pthread
MODULES =	lang/go
BUILD_DEPENDS =	devel/promu

do-build:
	cd ${WRKSRC} && GOPATH=${MODGO_WORKSPACE} GO111MODULE=on \
		${LOCALBASE}/bin/promu -v --config .promu-cgo.yml build

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/node_exporter ${PREFIX}/bin
	${INSTALL_DATA_DIR} ${PREFIX}/share/examples/node_exporter/
	${INSTALL_DATA} ${WRKSRC}/text_collector_examples/* \
		${PREFIX}/share/examples/node_exporter/

.include <bsd.port.mk>
