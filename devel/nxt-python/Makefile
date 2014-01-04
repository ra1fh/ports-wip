# $OpenBSD: Makefile,v 1.8 2013/03/10 22:28:05 espie Exp $

COMMENT =		Python library to control NXT

MODPY_EGG_VERSION =	2.2.2
DISTNAME =		nxt-python-${MODPY_EGG_VERSION}
PKGNAME =		nxt-python-${MODPY_EGG_VERSION}
CATEGORIES =		devel

HOMEPAGE =		http://code.google.com/p/nxt-python/

# GPLv3
PERMIT_PACKAGE_CDROM =		Yes

MASTER_SITES =	http://nxt-python.googlecode.com/files/

MODULES =	lang/python

RUN_DEPENDS =	devel/pyusb
WANTLIB =	${MODPY_WANTLIB}

MAKE_ENV +=	CFLAGS="${CFLAGS} -I${LOCALBASE}/include" \
		LDFLAGS="-L${LOCALBASE}/lib"

post-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/nxt-python
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/nxt-python/examples
	${INSTALL_DATA} ${WRKSRC}/README ${PREFIX}/share/doc/nxt-python
	${INSTALL_DATA} ${WRKSRC}/examples/* ${PREFIX}/share/doc/nxt-python/examples

.include <bsd.port.mk>
