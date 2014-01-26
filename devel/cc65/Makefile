# $OpenBSD$

COMMENT=		cross development package for 6502 systems

DISTNAME=		cc65-sources-2.13.3
PKGNAME=    		cc65-2.13.3
EXTRACT_SUFX= 		.tar.bz2
WRKDIST=		${WRKDIR}/cc65-2.13.3

CATEGORIES=		devel

HOMEPAGE=		http://www.cc65.org/

PERMIT_PACKAGE_CDROM=	No
PERMIT_PACKAGE_FTP=	No
PERMIT_DISTFILES_FTP=	No

WANTLIB += c m

BUILD_DEPENDS=		textproc/sgmlformat

MASTER_SITES = 		http://cc65.oldos.net/

USE_GMAKE = 		Yes

MAKE_FILE = 		make/gcc.mak

.include <bsd.port.mk>
