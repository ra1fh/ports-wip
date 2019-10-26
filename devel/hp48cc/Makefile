# $OpenBSD:$

COMMENT =		C-linke compiler that translates to H48 RPN
DISTNAME =		hp48cc-1.3
PKGNAME =		$(DISTNAME)

CATEGORIES =		devel

HOMEPAGE =		http://www.sigala.it/sandro/download.php

MAINTAINER =		Ralf Horstmann <ralf+ports@ackstorm.de>

# GPLv2+ LGPLv2+
PERMIT_DISTFILES =	Yes
PERMIT_PACKAGE =	Yes

WANTLIB = c

MASTER_SITES =		http://www.sigala.it/sandro/files/

CONFIGURE_STYLE =	gnu
CONFIGURE_ENV =		CPPFLAGS="-I${LOCALBASE}/include" CFLAGS="-L${LOCALBASE}/lib"


.include <bsd.port.mk>
