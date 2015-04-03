# $OpenBSD$

COMMENT =		Formatting Objects Processor

DISTNAME =		fop-1.1

CATEGORIES =		textproc

HOMEPAGE =		https://xmlgraphics.apache.org/fop/

# Apache License, version 2.0
PERMIT_PACKAGE_CDROM =	Yes

MASTER_SITES =		http://archive.apache.org/dist/xmlgraphics/fop/source/

DISTFILES =		fop-1.1-src.tar.gz

MODULES =		java
MODJAVA_VER =		1.7+
MODJAVA_BUILD =		ant

BUILD_DEPENDS =		devel/apache-ant

FOPHOME = 		${PREFIX}/share/fop
FOPDOCS = 		${PREFIX}/share/doc/java/fop

do-install:
	${INSTALL_DATA_DIR} ${FOPHOME}/bin
	${INSTALL_DATA_DIR} ${FOPHOME}/build
	${INSTALL_DATA_DIR} ${FOPHOME}/lib
	${INSTALL_DATA_DIR} ${FOPDOCS}/
	${INSTALL_SCRIPT} ${WRKSRC}/fop ${FOPHOME}/bin/fop
	ln -s ${TRUEPREFIX}/share/fop/bin/fop ${PREFIX}/bin/fop
	${INSTALL_DATA} ${WRKSRC}/build/*.jar ${FOPHOME}/build
	${INSTALL_DATA} ${WRKSRC}/lib/*.jar ${FOPHOME}/lib
	cd ${WRKSRC} && ${INSTALL_DATA} LICENSE README NOTICE KEYS ${FOPDOCS}/

.include <bsd.port.mk>
