# $OpenBSD$

COMMENT=		ACME crossassembler for multiple environments

SVNCOMMIT=		r325
DISTNAME=		acme-crossass-code-0-$(SVNCOMMIT)-trunk
PKGNAME=    		acme-0.97.325
EXTRACT_SUFX= 		.zip
WRKDIST=		${WRKDIR}/acme-crossass-code-0-$(SVNCOMMIT)-trunk

CATEGORIES=		devel

HOMEPAGE=		http://sourceforge.net/p/acme-crossass/
PERMIT_PACKAGE=		Yes



WANTLIB += 		c m

MASTER_SITES = 		https://sourceforge.net/code-snapshots/svn/a/ac/acme-crossass/code-0/

do-build:
	cd ${WRKSRC}/src && $(MAKE_PROGRAM) CC=cc

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/src/acme ${PREFIX}/bin/acme
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/acme
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/acme/cputypes
	${INSTALL_DATA} ${WRKSRC}/docs/*.txt ${PREFIX}/share/doc/acme
	${INSTALL_DATA} ${WRKSRC}/docs/COPYING ${PREFIX}/share/doc/acme
	${INSTALL_DATA} ${WRKSRC}/docs/cputypes/*.txt ${PREFIX}/share/doc/acme/cputypes


.include <bsd.port.mk>
