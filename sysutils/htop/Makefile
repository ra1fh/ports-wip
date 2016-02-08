# $OpenBSD$

COMMENT=		htop is an interactive text-mode process viewer

V =			20150203
GH_ACCOUNT =		hishamhm
GH_PROJECT =		htop
GH_COMMIT = 		5c593fae4227651075cfc9445f17dad6ae0a0b47

DISTNAME =		${GH_PROJECT}-${V}

CATEGORIES=		sysutils

HOMEPAGE=		https://github.com/hishamhm/htop

PERMIT_PACKAGE_CDROM=	Yes

WANTLIB += 		c m

AUTOCONF_VERSION =	2.69
AUTOMAKE_VERSION =	1.15

BUILD_DEPENDS=		

CONFIGURE_STYLE =	gnu

pre-configure:
	cd ${WRKSRC} && AUTOMAKE_VERSION=${AUTOMAKE_VERSION} \
	    AUTOCONF_VERSION=${AUTOCONF_VERSION} ./autogen.sh

.include <bsd.port.mk>
