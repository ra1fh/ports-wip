# $OpenBSD$

COMMENT=		HP Tools for HP48/49/50 calculators

DISTNAME=		hptools-src-3.0.8
PKGNAME=    		hptools-3.0.8

WRKDIST=		${WRKDIR}/Hptools

CATEGORIES=		devel

HOMEPAGE=		https://www.hpcalc.org/details/4263

PERMIT_PACKAGE=		No
PERMIT_DISTFILES=	No

WANTLIB += 		c

MASTER_SITES =		https://www.hpcalc.org/hp48/pc/programming/

do-build:
	cd ${WRKSRC} && $(MAKE_PROGRAM) rev=build
	cd ${WRKSRC}/build && $(MAKE_PROGRAM)

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/build/makerom ${PREFIX}/bin/
	${INSTALL_PROGRAM} ${WRKSRC}/build/rplcomp ${PREFIX}/bin/
	${INSTALL_PROGRAM} ${WRKSRC}/build/sasm    ${PREFIX}/bin/
	${INSTALL_PROGRAM} ${WRKSRC}/build/sload   ${PREFIX}/bin/
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/hptools
	${INSTALL_DATA} ${WRKSRC}/doc/CHANGES ${PREFIX}/share/doc/hptools/
	${INSTALL_DATA} ${WRKSRC}/doc/COPYING ${PREFIX}/share/doc/hptools/
	${INSTALL_DATA} ${WRKSRC}/doc/DOCS ${PREFIX}/share/doc/hptools/
	${INSTALL_DATA} ${WRKSRC}/doc/README ${PREFIX}/share/doc/hptools/
	${INSTALL_DATA} ${WRKSRC}/doc/*.DOC ${PREFIX}/share/doc/hptools/


.include <bsd.port.mk>
