# $OpenBSD$

COMMENT=	browser based analytic dashboard

V=		3.1.1
PKGNAME=	grafana-${V}
DISTNAME =	grafana-${V}

CATEGORIES=	www

HOMEPAGE=	https://www.grafana.org

MAINTAINER =	Ralf Horstmann <ralf-lists@ackstorm.de>

# Apache
PERMIT_PACKAGE_CDROM=	Yes

GH_ACCOUNT =	grafana
GH_PROJECT =	grafana
GH_TAGNAME =	v3.1.1
# from https://grafanarel.s3.amazonaws.com/builds/grafana-3.1.1-1470047149.linux-x64.tar.gz
GRAFANAREL=	grafana-${V}-1470047149
SUPDISTFILES=	${GRAFANAREL}.linux-x64.tar.gz

MODULES=	lang/go

do-build:
	${TAR} -C ${WRKSRC} -xzf ${FULLDISTDIR}/grafana-3.1.1-1470047149.linux-x64.tar.gz
	cd ${WRKSRC} && GOPATH=${MODGO_WORKSPACE} go run build.go build

LOCALSTATEDIR=	${BASELOCALSTATEDIR}/grafana
SYSCONFDIR=	${BASESYSCONFDIR}/grafana

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/bin/grafana-cli ${PREFIX}/bin
	${INSTALL_PROGRAM} ${WRKSRC}/bin/grafana-server ${PREFIX}/bin
	${INSTALL_DATA_DIR} ${PREFIX}/share/examples/grafana
	${INSTALL_DATA_DIR} ${PREFIX}/share/grafana/conf
	${INSTALL_DATA_DIR} ${PREFIX}/share/grafana/public
	${INSTALL_DATA_DIR} ${PREFIX}/share/grafana/vendor
	${INSTALL_DATA_DIR} ${PREFIX}/share/grafana/vendor/phantomjs
	${INSTALL_DATA} ${WRKSRC}/${GRAFANAREL}/conf/sample.ini \
		${PREFIX}/share/examples/grafana/grafana.ini
	${INSTALL_DATA} ${WRKSRC}/${GRAFANAREL}/conf/defaults.ini \
		${PREFIX}/share/grafana/conf/defaults.ini
	${INSTALL_DATA} ${WRKSRC}/${GRAFANAREL}/vendor/phantomjs/render.js \
		${PREFIX}/share/grafana/vendor/phantomjs/
	@cp -R ${WRKSRC}/${GRAFANAREL}/public ${PREFIX}/share/grafana
	@chmod -R u=rwX,go=rX ${PREFIX}/share/grafana/

.include <bsd.port.mk>
