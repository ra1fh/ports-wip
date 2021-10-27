# $OpenBSD$

COMMENT=		Intel 8085 Assembler with expressions and directives

V =			20191111
GH_ACCOUNT =		TomNisbet
GH_PROJECT =		asm85
GH_COMMIT =		c98cc8cbe2548b5ed85e64f04f5af1ed7bb7bfdb

DISTNAME=		${GH_PROJECT}-${V}

CATEGORIES=		devel

HOMEPAGE=		https://github.com/TomNisbet/asm85

# MIT
PERMIT_PACKAGE=		Yes

WANTLIB += 		c

do-build:
	cd ${WRKSRC}/src && $(MAKE_PROGRAM)

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/src/asm85 ${PREFIX}/bin/asm85
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/asm85
	${INSTALL_DATA} ${WRKSRC}/examples/*.asm ${PREFIX}/share/doc/asm85

.include <bsd.port.mk>
