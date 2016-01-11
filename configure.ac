m4_define([s2_major], [1])
m4_define([s2_minor], [0])
m4_define([s2_patch], [0])

AC_INIT([s2],
        [s2.major.s2.minor.s2.patch])
AC_CONFIG_MACRO_DIR([m4])
AC_CONFIG_HEADER(config.h)

# The gflags are used for automake, not GCC!
AM_INIT_AUTOMAKE([-Wall -Werror foreign subdir-objects])

# Required by Automake 1.12, but not recognised in older versions.
m4_pattern_allow([AM_PROG_AR])
AM_PROG_AR

# Adding libtool support
LT_INIT
AC_PROG_LIBTOOL

AX_CHECK_COMPILE_FLAG([-funsigned-char], [CXXFLAGS="$CXXFLAGS -funsigned-char"])
AX_CHECK_COMPILE_FLAG([-O3], [CXXFLAGS="$CXXFLAGS -O3"])
AX_CHECK_COMPILE_FLAG([-mmmx], [CXXFLAGS="$CXXFLAGS -mmmx"])
AX_CHECK_COMPILE_FLAG([-msse], [CXXFLAGS="$CXXFLAGS -msse"])
AX_CHECK_COMPILE_FLAG([-msse2], [CXXFLAGS="$CXXFLAGS -msse2"])

# Checks for programs.
AC_LANG([C++])
AC_PROG_CXX
AC_PROG_CC
AM_PROG_CC_C_O
AC_PROG_CPP

# Let the Makefile know if we're gcc
AM_CONDITIONAL(GCC, test "$GCC" = yes)

# Check for libraries.
PKG_CHECK_MODULES(GFLAGS, libgflags)

# Check for header files.
AC_CHECK_HEADERS([gflags/gflags.h], [],
                 AC_MSG_ERROR([gflags library is required. See INSTALL file.]))

AC_CONFIG_FILES([Makefile geometry/Makefile])
AC_OUTPUT

