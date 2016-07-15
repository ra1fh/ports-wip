# $OpenBSD$

COMMENT=		6502/65C02/65816/CPU64/65DTV02 cross assembler

DISTNAME=		64tass-1.52.1229-src
PKGNAME=    		64tass-1.52.1229
EXTRACT_SUFX= 		.zip
WRKDIST=		${WRKDIR}/${PKGNAME}-src

CATEGORIES=		devel

HOMEPAGE=		http://singularcrew.hu/64tass/

PERMIT_PACKAGE_CDROM=	Yes
PERMIT_PACKAGE_FTP=	Yes
PERMIT_DISTFILES_FTP=	Yes

USE_GMAKE =		Yes

WANTLIB += 		c

MASTER_SITES =		${MASTER_SITE_SOURCEFORGE:=tass64/source/}

do-build:
	cd ${WRKSRC} && $(MAKE_PROGRAM)

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/64tass ${PREFIX}/bin/64tass
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/64tass
	${INSTALL_DATA} ${WRKSRC}/README* ${PREFIX}/share/doc/64tass


.include <bsd.port.mk>
