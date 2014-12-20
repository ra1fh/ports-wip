# $OpenBSD$

COMMENT=		extensible emacs interface for TeX

DISTNAME=		auctex-11.88
#REVISION=		0
CATEGORIES=		print

HOMEPAGE=		http://www.gnu.org/software/auctex/

# GPL
PERMIT_PACKAGE_CDROM=	Yes
PERMIT_PACKAGE_FTP=	Yes
PERMIT_DISTFILES_FTP=	Yes

MASTER_SITES=		${MASTER_SITE_GNU:=auctex/}

RUN_DEPENDS=		emacs->=24,<25:editors/emacs \
			print/texlive/base
BUILD_DEPENDS=		emacs->=24,<25:editors/emacs \
			print/texlive/base

USE_GMAKE=			Yes

CONFIGURE_STYLE=	gnu
CONFIGURE_ARGS=		--with-lispdir=${PREFIX}/share/emacs/site-lisp

post-install:
	@chown -R ${SHAREOWN}:${SHAREGRP} ${PREFIX}/share/emacs/site-lisp/auctex

.include <bsd.port.mk>
