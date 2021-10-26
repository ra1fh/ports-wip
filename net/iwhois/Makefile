
COMMENT =	Intelligent WHOIS client

V =		5.5.10
DISTNAME =	whois
PKGNAME =	iwhois-${V}

CATEGORIES =	net

HOMEPAGE =	https://github.com/rfc1036/whois

MAINTAINER =	Ralf Horstmann <ralf@ackstorm.de>

# GPLv2
PERMIT_PACKAGE =	Yes
PERMIT_DISTFILES =	Yes

WANTLIB =		c idn2

MASTER_SITES =		http://deb.debian.org/debian/pool/main/w/whois/

DISTFILES =		whois_${V}.tar.xz

EXTRACT_SUFX =		.tar.xz

BUILD_DEPENDS =		devel/gettext,-tools
LIB_DEPENDS =		devel/libidn2

MAKE_FLAGS =		prefix=${PREFIX}

USE_GMAKE =		Yes

.include <bsd.port.mk>
