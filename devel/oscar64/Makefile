# $OpenBSD$

COMMENT=		Optimizing C Compiler Assembler and Runtime for C64

GH_ACCOUNT =		drmortalwombat
GH_PROJECT =		oscar64
GH_TAGNAME =		v1.26.229

CATEGORIES=		devel

HOMEPAGE=		https://github.com/drmortalwombat/oscar64

# GPLv3
PERMIT_PACKAGE=		Yes

WANTLIB += 		c

USE_GMAKE = 		Yes

MAKE_ENV +=		DATAPATH=${PREFIX}/share/oscar64

do-build:
	mkdir -p ${WRKSRC}/build \
	&& cd ${WRKSRC}/build \
	&& ${SETENV} ${MAKE_ENV} ${MAKE_PROGRAM} -f ../make/makefile

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/bin/oscar64 ${PREFIX}/bin/oscar64
	${INSTALL_DATA_DIR} ${PREFIX}/share/oscar64
.for dir in include samples
	cp -Rp ${WRKSRC}/${dir} ${PREFIX}/share/oscar64/
.endfor

.include <bsd.port.mk>
