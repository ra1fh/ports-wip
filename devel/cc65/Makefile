# $OpenBSD$

COMMENT=		cross development package for 6502 systems

GH_ACCOUNT =		cc65
GH_PROJECT =		cc65
GH_TAGNAME =		V2.19

CATEGORIES=		devel

HOMEPAGE=		https://cc65.github.io/cc65/

# ZLIB license
PERMIT_PACKAGE=		Yes

WANTLIB += 		c m

BUILD_DEPENDS=		textproc/linuxdoc-tools

USE_GMAKE = 		Yes
ALL_TARGET =		all doc

do-install:
	cd ${WRKBUILD} && umask 022 && exec ${_FAKESUDO} \
	${SETENV} PREFIX=${WRKINST}${LOCALBASE} \
	${MAKE_PROGRAM} -f ${MAKE_FILE} ${FAKE_TARGET}


.include <bsd.port.mk>
