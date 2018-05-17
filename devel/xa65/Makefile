# $OpenBSD$

COMMENT=		open source 6502 cross assembler

DISTNAME=		xa-2.3.8

CATEGORIES=		devel

HOMEPAGE=		http://www.floodgap.com/retrotech/xa/

PERMIT_PACKAGE_CDROM=	Yes
PERMIT_PACKAGE_FTP=	Yes
PERMIT_DISTFILES_FTP=	Yes

WANTLIB += 		c

MASTER_SITES = 		http://www.floodgap.com/retrotech/xa/dists/

post-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/xa
	${INSTALL_DATA} ${WRKSRC}/doc/fileformat.txt ${PREFIX}/share/doc/xa

.include <bsd.port.mk>
