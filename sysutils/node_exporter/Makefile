# $OpenBSD$

COMMENT =		prometheus node_exporter

DISTNAME = 		node_exporter-0.16.0.git
GH_ACCOUNT =		prometheus
GH_PROJECT =		node_exporter
GH_COMMIT =		5a461d261c99ed9479e491c97cfd3bfe310a4139
WRKDIST =		${WRKDIR}/${GH_PROJECT}-${GH_COMMIT}

CATEGORIES =		sysutils

HOMEPAGE =		http://prometheus.io/

# Apache 2.0
MAINTAINER =		Ralf Horstmann <ralf-lists@ackstorm.de>

PERMIT_PACKAGE_CDROM =	Yes

WANTLIB =		c pthread

USE_GMAKE = 		Yes

MODULES=		lang/go

do-build:
	cd ${WRKSRC} && ${MODGO_ENV} go build -tags nosystemd

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/node_exporter ${PREFIX}/bin
	${INSTALL_DATA_DIR} ${WRKINST}/${SYSCONFDIR}/rc.d
	${INSTALL_DATA} ${PKGDIR}/nodeexporter.rc ${WRKINST}/${SYSCONFDIR}/rc.d/nodeexporter

.include <bsd.port.mk>
