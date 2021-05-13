# $OpenBSD$

COMMENT=		dreamass is a cross assembler for 6510 and compatible

V =			20210412
GH_ACCOUNT =		docbacardi
GH_PROJECT =		dreamass
GH_COMMIT =		bc34eb3d622b0e29cf8688986efcf77b3bf89420

DISTNAME=		${GH_PROJECT}-${V}

CATEGORIES=		devel

HOMEPAGE=		http://sourceforge.net/projects/rrtools/ \
			https://github.com/docbacardi/dreamass

# GPLv2
PERMIT_PACKAGE=		Yes

WANTLIB += 		c

USE_GMAKE = Yes

do-build:
	cd ${WRKSRC} && $(MAKE_PROGRAM)
	cd ${WRKSRC}/docs && $(MAKE_PROGRAM)

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/dreamass ${PREFIX}/bin/dreamass
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/dreamass
	${INSTALL_DATA} ${WRKSRC}/docs/dreamass.txt ${PREFIX}/share/doc/dreamass/
	${INSTALL_DATA} ${WRKSRC}/docs/dreamass.html ${PREFIX}/share/doc/dreamass/
	${INSTALL_DATA} ${WRKSRC}/docs/*.info ${PREFIX}/info/

.include <bsd.port.mk>
