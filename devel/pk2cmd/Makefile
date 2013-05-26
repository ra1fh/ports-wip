# $OpenBSD$

COMMENT=	PICkit 2 Command Line Interface

DISTNAME=		pk2cmdv1.20LinuxMacSource
PKGNAME=    	pk2cmd-1.20
EXTRACT_SUFX= 	.tar.gz
WRKDIST=		${WRKDIR}/pk2cmdv1.20LinuxMacSource

CATEGORIES=	devel

HOMEPAGE= http://www.microchip.com/stellent/idcplg?IdcService=SS_GET_PAGE&nodeId=1406&dDocName=en023805

PERMIT_PACKAGE_CDROM=	Yes
PERMIT_PACKAGE_FTP=	Yes
PERMIT_DISTFILES_FTP=	Yes

USE_GMAKE = Yes

MASTER_SITES = http://ww1.microchip.com/downloads/en/DeviceDoc/

WANTLIB += c

LIB_DEPENDS = devel/libusb-compat

do-build:
	cd ${WRKSRC} && $(MAKE_PROGRAM) linux

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/pk2cmd ${PREFIX}/bin/pk2cmd
	${INSTALL_DATA_DIR} ${PREFIX}/share/pk2cmd
	${INSTALL_DATA} ${WRKSRC}/PK2DeviceFile.dat ${PREFIX}/share/pk2cmd

.include <bsd.port.mk>
