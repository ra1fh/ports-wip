COMMENT =		plantuml UML diagram generator

V = 			1.2023.6
DISTNAME =		v${V}
PKGNAME =  		plantuml-${V}
EXTRACT_SUFX = 	.zip
WRKDIST=		${WRKDIR}/plantuml-${V}

PKG_ARCH =		*

CATEGORIES =		devel

HOMEPAGE =		http://plantuml.sourceforge.net
SITES =			https://github.com/plantuml/plantuml/archive/refs/tags/

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
	cd ${WRKSRC} && ${SETENV} ${MAKE_ENV} gradle --no-daemon \
		--offline --stacktrace build
#	cd ${WRKSRC} && gradle --no-daemon build

do-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/plantuml
	${INSTALL_DATA} ${WRKSRC}/build/libs/plantuml-${V}.jar ${PREFIX}/share/plantuml/plantuml.jar
	echo '#!/bin/sh\n$$(javaPathHelper -c plantuml) -jar' \
		'${TRUEPREFIX}/share/plantuml/plantuml.jar "$$@"' \
		 > ${PREFIX}/bin/plantuml
	chmod +x ${PREFIX}/bin/plantuml

.include <bsd.port.mk>
