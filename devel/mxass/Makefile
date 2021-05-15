# $OpenBSD$

COMMENT=	cross assembler that targets Commodore 64-like platforms

V=		20141206
GH_ACCOUNT=	mist64
GH_PROJECT=	mxass
GH_COMMIT= 	ea6232621d95c9a0b4a46d43f697ffab2eb0987f

DISTNAME=	${GH_PROJECT}-${V}

CATEGORIES=	devel

HOMEPAGE=	https://github.com/mist64/mxass

PERMIT_PACKAGE=	Yes

WANTLIB+= 	c

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/mxass ${PREFIX}/bin
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/mxass
	${INSTALL_DATA} ${WRKSRC}/mxass.txt ${PREFIX}/share/doc/mxass
	${INSTALL_DATA_DIR} ${PREFIX}/share/mxass
	${INSTALL_DATA} ${WRKSRC}/OPCODES.A18 ${PREFIX}/share/mxass
	${INSTALL_DATA} ${WRKSRC}/OPZ80.A23   ${PREFIX}/share/mxass

.include <bsd.port.mk>
