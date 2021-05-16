# $OpenBSD$

COMMENT=		cross-assembler for the 65xx series

V =			2.1
MODPY_EGG_VERSION =	${V}
GH_ACCOUNT =		michaelcmartin
GH_PROJECT =		Ophis
GH_TAGNAME = 		v2.1

DISTNAME =		ophis-${V}

CATEGORIES =		devel

HOMEPAGE =		https://github.com/michaelcmartin/Ophis

# MIT license
PERMIT_PACKAGE =	Yes

MODULES =		lang/python
MODPY_SETUPUTILS = 	No
WRKSRC =		${WRKDIST}/src

FLAVORS =		python3
FLAVOR ?=

post-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/ophis
	cd ${WRKDIST} && cp -r examples ${PREFIX}/share/doc/ophis
	cd ${WRKDIST} && cp -r platform ${PREFIX}/share/doc/ophis
	${INSTALL_DATA} ${WRKDIST}/doc/ophismanual.pdf ${PREFIX}/share/doc/ophis

.include <bsd.port.mk>
