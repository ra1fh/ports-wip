# $OpenBSD$

COMMENT=		cross development package for 6502 systems

V =			2.19
REVISION =		1
GH_ACCOUNT =		cc65
GH_PROJECT =		cc65
#GH_TAGNAME =		V2.19
GH_COMMIT = 		3dfe0330003f19680f2afc9a607bea397b5c9fec

DISTNAME =		${GH_PROJECT}-${V}

CATEGORIES=		devel

HOMEPAGE=		https://cc65.github.io/cc65/

# ZLIB license
PERMIT_PACKAGE=		Yes

WANTLIB += 		c m

BUILD_DEPENDS=		textproc/linuxdoc-tools

USE_GMAKE = 		Yes
ALL_TARGET =		all doc
PATCHORIG =		.orig

do-install:
	cd ${WRKBUILD} && umask 022 && exec ${_FAKESUDO} \
	${SETENV} PREFIX=${WRKINST}${LOCALBASE} \
	${MAKE_PROGRAM} -f ${MAKE_FILE} ${FAKE_TARGET}


.include <bsd.port.mk>
