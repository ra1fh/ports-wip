# $OpenBSD$

COMMENT=		dreamass is a cross assembler for 6510 and compatible

V =			20140504
GH_ACCOUNT =		docbacardi
GH_PROJECT =		dreamass
GH_COMMIT =		ba43fe1a1cc038a617e6afc11363a72606e2f91e

DISTNAME=		${GH_PROJECT}-${V}

CATEGORIES=		devel

HOMEPAGE=		http://sourceforge.net/projects/rrtools/ \
			https://github.com/docbacardi/dreamass

PERMIT_PACKAGE_CDROM=	Yes
PERMIT_PACKAGE_FTP=	Yes
PERMIT_DISTFILES_FTP=	Yes

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
