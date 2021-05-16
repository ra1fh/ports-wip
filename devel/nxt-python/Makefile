# $OpenBSD$

COMMENT =		Python library to control NXT

MODPY_EGG_VERSION =	2.2.2

GH_ACCOUNT =		Eelviny
GH_PROJECT =		nxt-python
GH_TAGNAME = 		v${MODPY_EGG_VERSION}

DISTNAME =		nxt-python-${MODPY_EGG_VERSION}
CATEGORIES =		devel
HOMEPAGE =		https://github.com/Eelviny/nxt-python

# GPLv3
PERMIT_PACKAGE =	Yes

MODULES =		lang/python

RUN_DEPENDS =		devel/pyusb${MODPY_FLAVOR}
WANTLIB =		${MODPY_WANTLIB}

MAKE_ENV +=		CFLAGS="${CFLAGS} -I${LOCALBASE}/include" \
			LDFLAGS="-L${LOCALBASE}/lib"

FLAVORS =		python3
FLAVOR ?=

post-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/nxt-python
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/nxt-python/examples
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/nxt-python/examples/mindsensors
	${INSTALL_DATA} ${WRKSRC}/README ${PREFIX}/share/doc/nxt-python
	${INSTALL_DATA} ${WRKSRC}/examples/*.py ${PREFIX}/share/doc/nxt-python/examples
	${INSTALL_DATA} ${WRKSRC}/examples/mindsensors/*.py ${PREFIX}/share/doc/nxt-python/examples/mindsensors

.include <bsd.port.mk>
