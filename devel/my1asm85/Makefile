# $OpenBSD$

COMMENT=	Cross Assembler for Intel 8085 Microprocessor
V =		20210214
NAME =		my1asm85

PKGNAME=	my1asm85-${V}
DISTNAME=	my1asm85
DISTFILES=	my1asm85-src-${V}.tar.bz2

CATEGORIES=	devel

HOMEPAGE=	https://codeberg.org/azman/my1asm85.git

# BSD
PERMIT_PACKAGE=	Yes

USE_GMAKE=	Yes

WANTLIB += 	c

do-build:
	cd ${WRKSRC} && $(MAKE_PROGRAM) CC=cc CXX=c++

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/my1asm85 ${PREFIX}/bin/my1asm
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/my1asm85
	${INSTALL_DATA} ${WRKSRC}/asm/monitor85.asm ${PREFIX}/share/doc/my1asm85

.include <bsd.port.mk>
