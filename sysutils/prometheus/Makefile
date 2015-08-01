# $OpenBSD$

COMMENT =		prometheus monitoring
DISTNAME =		prometheus-0.15.1

CATEGORIES =		sysutils

HOMEPAGE =		http://prometheus.io/

MAINTAINER =		Ralf Horstmann <ralf-lists@ackstorm.de>

PERMIT_PACKAGE_CDROM =	Yes

# "make port-lib-depends-check" can help
WANTLIB =		c pthread

USE_GMAKE = 		Yes

GH_ACCOUNT =		prometheus
GH_PROJECT =		prometheus
GH_TAGNAME =		0.15.1
#GH_COMMIT =		85100767f75a5866527150fae271e9a3c8ea66a8

BUILD_DEPENDS=	lang/go

do-build:
	cd ${WRKSRC} && ${MAKE_PROGRAM} build

do-install:
	${INSTALL_DATA_DIR} ${WRKINST}/${SYSCONFDIR}/prometheus
	${INSTALL_DATA_DIR} ${WRKINST}/${SYSCONFDIR}/rc.d
	${INSTALL_DATA_DIR} ${WRKINST}/var/prometheus
	${INSTALL_DATA_DIR} ${PREFIX}/share/examples/prometheus/consoles
	${INSTALL_DATA_DIR} ${PREFIX}/share/examples/prometheus/console_libraries
	${INSTALL_PROGRAM} ${WRKSRC}/prometheus ${PREFIX}/bin
	${INSTALL_PROGRAM} ${WRKSRC}/promtool ${PREFIX}/bin
	${INSTALL_DATA} ${WRKSRC}/consoles/* ${PREFIX}/share/examples/prometheus/consoles/
	${INSTALL_DATA} ${WRKSRC}/console_libraries/{menu.lib,prom.lib} ${PREFIX}/share/examples/prometheus/console_libraries
	${INSTALL_DATA} ${PKGDIR}/prometheus.yml ${PREFIX}/share/examples/prometheus/prometheus.yml
	${INSTALL_DATA} ${PKGDIR}/prometheus.rc ${WRKINST}/${SYSCONFDIR}/rc.d/prometheus

.include <bsd.port.mk>
