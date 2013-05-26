# $OpenBSD$

COMMENT=	c64 cross assembler

DISTNAME=	dasm-2.20.11
CATEGORIES=	devel

HOMEPAGE=	http://dasm-dillon.sourceforge.net/

PERMIT_PACKAGE_CDROM=	Yes
PERMIT_PACKAGE_FTP=	Yes
PERMIT_DISTFILES_FTP=	Yes

USE_GMAKE = Yes

WANTLIB += c

MASTER_SITES = ${MASTER_SITE_SOURCEFORGE:=dasm-dillon/}

do-build:
	cd ${WRKSRC}/src && $(MAKE_PROGRAM)
	cd ${WRKSRC} && $(MAKE_PROGRAM)

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/bin/dasm ${PREFIX}/bin/dasm
	${INSTALL_PROGRAM} ${WRKSRC}/bin/ftohex ${PREFIX}/bin/ftohex
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/dasm
	${INSTALL_DATA} ${WRKSRC}/doc/*.txt ${PREFIX}/share/doc/dasm


.include <bsd.port.mk>
