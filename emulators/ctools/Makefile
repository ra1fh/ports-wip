# $OpenBSD$

COMMENT =		programs for accessing C64 and C128 CP/M disk images

V =			0.4a
GH_ACCOUNT =		mist64
GH_PROJECT =		ctools
GH_COMMIT = 		1b68ab4a08b854baf37c1607b3049c6a6f74a5a4

DISTNAME =		${GH_PROJECT}-${V}

CATEGORIES =		emulators

HOMEPAGE =		https://github.com/mist64/ctools

# GPLv2+
PERMIT_PACKAGE =	Yes

WANTLIB += 		c

USE_GMAKE = 		Yes
WRKBUILD =		${WRKSRC}/src

do-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/ctools
	${INSTALL_DATA} ${WRKSRC}/{COPYING,README} ${PREFIX}/share/doc/ctools
	cd ${WRKBUILD} && ${INSTALL_PROGRAM} d64dump biosdump cformat ctools ${PREFIX}/bin
	${INSTALL_MAN} ${WRKSRC}/doc/{biosdump.1,cformat.1,ctools.1,d64dump.1} \
		${PREFIX}/man/man1/
	${INSTALL_MAN} ${WRKSRC}/doc/d64.5 \
		${PREFIX}/man/man5/


.include <bsd.port.mk>
