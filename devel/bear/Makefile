# $OpenBSD$

COMMENT=		Tool that generates a compilation database for clang tooling

GH_ACCOUNT =		rizsotto
GH_PROJECT =		Bear
GH_TAGNAME =		2.4.4

CATEGORIES=		devel

HOMEPAGE=		https://github.com/rizsotto/Bear/

PERMIT_PACKAGE=		Yes

WANTLIB += 		c

do-build:
	cd ${WRKSRC} && cmake . && ${MAKE_ENV} ${MAKE_PROGRAMM}


.include <bsd.port.mk>
