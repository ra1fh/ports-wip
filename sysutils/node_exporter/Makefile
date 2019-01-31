# $OpenBSD$

COMMENT =		prometheus node_exporter

DISTNAME = 		node_exporter-0.17.0
GH_ACCOUNT =		prometheus
GH_PROJECT =		node_exporter
GH_TAGNAME =		v0.17.0

CATEGORIES =		sysutils

HOMEPAGE =		http://prometheus.io/

# Apache 2.0
MAINTAINER =		Ralf Horstmann <ralf-lists@ackstorm.de>

PERMIT_PACKAGE_CDROM =	Yes

WANTLIB =		c pthread

USE_GMAKE = 		Yes

MODULES=		lang/go

do-build:
	cd ${WRKSRC} && ${MODGO_CMD} build -tags nosystemd

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/node_exporter ${PREFIX}/bin
	${INSTALL_DATA_DIR} ${WRKINST}/${SYSCONFDIR}/rc.d
	${INSTALL_DATA} ${PKGDIR}/node_exporter.rc ${WRKINST}/${SYSCONFDIR}/rc.d/node_exporter

.include <bsd.port.mk>
