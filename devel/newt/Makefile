COMMENT =	library for terminal widgets

V =		0.52.25

DISTNAME =	newt-${V}
CATEGORIES =	devel
HOMEPAGE =	https://pagure.io/newt

SHARED_LIBS +=  newt 0.52

# LGPL-2.0-or-later
PERMIT_PACKAGE = Yes

# "make port-lib-depends-check" can help
#WANTLIB =		???
WANTLIB += c popt slang

SITES =			https://releases.pagure.org/newt/

DISTFILES =		newt-${V}.tar.gz

# Standard for C++ ports:
#COMPILER =		base-clang ports-gcc base-gcc
# Standard for C++11 or newer:
#COMPILER =		base-clang ports-gcc

# Any modules we may be using
#MODULES =		???

# Dependencies
BUILD_DEPENDS =		devel/libslang devel/popt
#RUN_DEPENDS =		???
LIB_DEPENDS =		devel/libslang devel/popt
#TEST_DEPENDS =		???

#MAKE_FLAGS =		???
#MAKE_ENV =		???
#FAKE_FLAGS =		???
#TEST_FLAGS =		???

# build/configuration variables
#
#SEPARATE_BUILD =	Yes
USE_GMAKE =		Yes
#USE_GROFF =		Yes
# Programs that require GNU libtool to build instead of the OpenBSD one
# should use this option. Add a comment explaining why. Don't use this if
# a port requires libtool's .m4 files but otherwise can use OpenBSD libtool,
# in that case use "BUILD_DEPENDS=devel/libtool" instead.
#USE_LIBTOOL=		gnu
# Set CONFIGURE_STYLE to value corresponding to some standard configuration
#	  perl [modbuild]: perl's MakeMaker Makefile.PL (modbuild: perl's
#	  Module::Build Build.PL)
#	  gnu [autoconf] [old] [dest]: gnu style configure (old: no
#	  sysconfdir), (dest: add DESTDIR, does not handle it),
#	  autoconf: run autoconf to regenerate configure script. implies gnu.
#	  autoreconf: run autoreconf (or other script passed in AUTORECONF) to
#	   generate configure. implies gnu. adds dependencies automatically.
#	XXX: cygnus products do NOT use autoconf for making the main
#		configure from configure.in
#	  imake [noman]: port uses imake for configuration.
#	  (noman: no man page installation)
#	  simple: port has its own configure script
#	  none: override default CONFIGURE_STYLE coming from a module
#	        (needed for some ports using lang/python, etc.)
CONFIGURE_STYLE =	gnu
#AUTORECONF =		./autogen.sh
#CONFIGURE_SCRIPT =	??? (if other than configure)
CONFIGURE_ARGS =	--disable-nls --without-python \
	--without-tcl --enable-year2038
CONFIGURE_ENV =		CPPFLAGS="${CPPFLAGS} -I${LOCALBASE}/include" \
	LDFLAGS="-L${LOCALBASE}/lib"

# common examples:
# - port has ready-generated autoconf configure script that can be used as-is:
#CONFIGURE_STYLE =	gnu
# - ready-generated script needs patching: preferably patch the input files
#   (configure.in, configure.ac, *.m4) rather than the generated script, this
#   is less likely to break during updates) - prefer to use the same version
#   of autoconf as was used upstream:
#CONFIGURE_STYLE =	gnu
#AUTOCONF_VERSION =	2.71
# - either no generated script was included (common with projects using git
#   archives), or both autoconf and automake input files need patching:
#CONFIGURE_STYLE =	autoreconf
#AUTOCONF_VERSION =	2.71
#AUTOMAKE_VERSION =	1.16
#AUTORECONF =		./autogen.sh (optional; "autoreconf --force --install"
#					is used by default)

# Is the build automagic or is it interactive
#
#IS_INTERACTIVE =		Yes
#TEST_IS_INTERACTIVE =		Yes

.include <bsd.port.mk>
