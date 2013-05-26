# $OpenBSD$

COMMENT=	6502/65C02/65816/CPU64/65DTV02 cross assembler

DISTNAME=		64tass_v1.46
PKGNAME=    	64tass-1.46
EXTRACT_SUFX= 	.tar.bz2
WRKDIST=		${WRKDIR}/${PKGNAME}

CATEGORIES=	devel

HOMEPAGE=	http://singularcrew.hu/64tass/

PERMIT_PACKAGE_CDROM=	Yes
PERMIT_PACKAGE_FTP=	Yes
PERMIT_DISTFILES_FTP=	Yes

USE_GMAKE = Yes

WANTLIB += c

MASTER_SITES = http://c64.rulez.org/pub/c64/IDE64/source/

do-build:
	cd ${WRKSRC} && $(MAKE_PROGRAM) -f Makefile2

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/64tass ${PREFIX}/bin/64tass
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/64tass
	${INSTALL_DATA} ${WRKSRC}/README* ${PREFIX}/share/doc/64tass


.include <bsd.port.mk>
