# $OpenBSD$

COMMENT =		Formatting Objects Processor

DISTNAME =		fop-1.1

CATEGORIES =		textproc

HOMEPAGE =		https://xmlgraphics.apache.org/fop/

# Apache License, version 2.0
PERMIT_PACKAGE_CDROM =	Yes

MASTER_SITES =		http://archive.apache.org/dist/xmlgraphics/fop/source/
MASTER_SITES0 = 	${MASTER_SITE_SOURCEFORGE:=offo/offo-hyphenation/2.1/}

DISTFILES =		offo-hyphenation.zip:0 fop-1.1-src.tar.gz 

MODULES =		java
MODJAVA_VER =		1.7+
MODJAVA_BUILD =		ant

BUILD_DEPENDS =		devel/apache-ant

FOPHOME = 		${PREFIX}/share/fop
FOPDOCS = 		${PREFIX}/share/doc/java/fop

post-extract:
	cd ${WRKSRC} && ${UNZIP} ${DISTDIR}/offo-hyphenation.zip
	cp ${WRKSRC}/offo-hyphenation/hyph/*.xml ${WRKSRC}/hyph

do-install:
	${INSTALL_DATA_DIR} ${FOPHOME}/build
	${INSTALL_DATA_DIR} ${FOPHOME}/conf
	${INSTALL_DATA_DIR} ${FOPHOME}/hyph
	${INSTALL_DATA_DIR} ${FOPHOME}/lib
	${INSTALL_DATA_DIR} ${FOPDOCS}/
	${INSTALL_SCRIPT} ${WRKSRC}/fop ${FOPHOME}/fop
	ln -s ${TRUEPREFIX}/share/fop/fop ${PREFIX}/bin/fop
	${INSTALL_DATA} ${WRKSRC}/build/*.jar ${FOPHOME}/build
	${INSTALL_DATA} ${WRKSRC}/lib/*.jar ${FOPHOME}/lib
	cd ${WRKSRC} && ${INSTALL_DATA} LICENSE README NOTICE KEYS ${FOPDOCS}/
	${INSTALL_DATA} ${WRKSRC}/hyph/*.xml ${FOPHOME}/hyph/
	${INSTALL_DATA} ${WRKSRC}/conf/fop.xconf ${FOPHOME}/conf/

.include <bsd.port.mk>
