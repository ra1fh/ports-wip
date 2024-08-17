# $OpenBSD$

COMMENT=		c64 cross assembler

DISTNAME=		dasm-2.20.11
CATEGORIES=		devel

HOMEPAGE=		http://dasm-dillon.sourceforge.net/

PERMIT_PACKAGE=		Yes

USE_GMAKE = 		Yes

WANTLIB += 		c

SITES = 		${SITE_SOURCEFORGE:=dasm-dillon/}

do-build:
	cd ${WRKSRC}/src && $(MAKE_PROGRAM) CC=cc
	cd ${WRKSRC} && $(MAKE_PROGRAM) CC=cc

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/bin/dasm ${PREFIX}/bin/dasm
	${INSTALL_PROGRAM} ${WRKSRC}/bin/ftohex ${PREFIX}/bin/ftohex
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/dasm
	${INSTALL_DATA} ${WRKSRC}/doc/*.txt ${PREFIX}/share/doc/dasm


.include <bsd.port.mk>
