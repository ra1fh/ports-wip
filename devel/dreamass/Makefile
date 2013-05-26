# $OpenBSD$

COMMENT=	dreamass is a cross assembler for 6510 and compatible

DISTNAME=		dreamass_src_20090110
PKGNAME=    	dreamass-20090110
WRKDIST=		${WRKDIR}/dreamass

CATEGORIES=	devel

HOMEPAGE=	http://developer.berlios.de/projects/rrtools/

PERMIT_PACKAGE_CDROM=	Yes
PERMIT_PACKAGE_FTP=	Yes
PERMIT_DISTFILES_FTP=	Yes

WANTLIB += c

MASTER_SITES = ${MASTER_SITE_BERLIOS:=rrtools/}

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
