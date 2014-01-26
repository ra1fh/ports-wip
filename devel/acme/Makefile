# $OpenBSD$

COMMENT=		ACME crossassembler for multiple environments

DISTNAME=		acme091src
PKGNAME=    		acme-0.91
EXTRACT_SUFX= 		.tar.bz2
WRKDIST=		${WRKDIR}/acme091

CATEGORIES=		devel

HOMEPAGE=		http://www.esw-heim.tu-clausthal.de/~marco/smorbrod/acme/

PERMIT_PACKAGE_CDROM=	Yes
PERMIT_PACKAGE_FTP=	Yes
PERMIT_DISTFILES_FTP=	Yes

WANTLIB += 		c

MASTER_SITES = 		http://www.esw-heim.tu-clausthal.de/~marco/smorbrod/acme/current/

do-build:
	cd ${WRKSRC}/src && $(MAKE_PROGRAM)

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/src/acme ${PREFIX}/bin/acme
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/acme
	${INSTALL_DATA} ${WRKSRC}/docs/* ${PREFIX}/share/doc/acme


.include <bsd.port.mk>
