COMMENT =		plantuml UML diagram generator

V = 			1.2021.6
REVISION =		0
DISTNAME =		plantuml-${V}
PKGNAME =  		plantuml-${V}

PKG_ARCH =		*

CATEGORIES =		devel

HOMEPAGE =		http://plantuml.sourceforge.net
MASTER_SITES =		${MASTER_SITE_SOURCEFORGE:=plantuml/}

PERMIT_PACKAGE =	Yes

WANTLIB =		c m pthread stdc++

MODULES =		java
MODJAVA_VER =		11

BUILD_DEPENDS =		devel/apache-ant
RUN_DEPENDS =		java/javaPathHelper \
			math/graphviz

MAKE_ENV =		JAVA_HOME=${JAVA_HOME} MAKE=${MAKE_PROGRAM}
ANT_CMD =		${SETENV} ${MAKE_ENV} PATH=${JAVA_HOME}/bin:${PATH} \
			${LOCALBASE}/bin/ant

do-build:
	cd ${WRKSRC} && ${ANT_CMD}

do-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/plantuml
	${INSTALL_DATA} ${WRKSRC}/plantuml.jar ${PREFIX}/share/plantuml
	echo '#!/bin/sh\n$$(javaPathHelper -c plantuml) -jar' \
		'${TRUEPREFIX}/share/plantuml/plantuml.jar "$$@"' \
		 > ${PREFIX}/bin/plantuml
	chmod +x ${PREFIX}/bin/plantuml

.include <bsd.port.mk>
