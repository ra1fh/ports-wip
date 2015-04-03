# $OpenBSD: Makefile,v 1.12 2013/03/11 10:50:27 espie Exp $

SHARED_ONLY=	Yes

COMMENT=		python interface to libusb
MODPY_EGG_VERSION=	1.0.0b2
DISTNAME=		pyusb-${MODPY_EGG_VERSION}
CATEGORIES=		devel
MASTER_SITES=		${MASTER_SITE_SOURCEFORGE:S,$,pyusb/PyUSB%201.0/1.0.0-beta-1/,}
FULLPKGNAME= ${DISTNAME}

HOMEPAGE=	http://sourceforge.net/apps/trac/pyusb/

# BSD
PERMIT_PACKAGE_CDROM=	Yes

NO_TEST=	Yes

MODULES=	lang/python

LIB_DEPENDS=	devel/libusb1 \
		${MODPY_LIB_DEPENDS}
WANTLIB =	${MODPY_WANTLIB}

pre-configure:
	@perl -pi -e 's|_LOCALBASE_|${LOCALBASE}|g' ${WRKSRC}/setup.py

post-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/examples/pyusb

.include <bsd.port.mk>
