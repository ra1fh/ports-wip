# $OpenBSD$

COMMENT=		ACME crossassembler for multiple environments

DISTNAME=		acme-crossass-code-0-54-trunk
PKGNAME=    		acme-0.95.5
EXTRACT_SUFX= 		.zip
WRKDIST=		${WRKDIR}/acme-crossass-code-0-54-trunk

CATEGORIES=		devel

HOMEPAGE=		http://www.esw-heim.tu-clausthal.de/~marco/smorbrod/acme/ \
			http://sourceforge.net/p/acme-crossass/

PERMIT_PACKAGE_CDROM=	Yes
PERMIT_PACKAGE_FTP=	Yes
PERMIT_DISTFILES_FTP=	Yes

WANTLIB += 		c m

MASTER_SITES = 		http://sourceforge.net/code-snapshots/svn/a/ac/acme-crossass/code-0/

do-build:
	cd ${WRKSRC}/src && $(MAKE_PROGRAM)

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/src/acme ${PREFIX}/bin/acme
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/acme
	${INSTALL_DATA} ${WRKSRC}/docs/* ${PREFIX}/share/doc/acme


.include <bsd.port.mk>
