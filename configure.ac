AC_INIT([protobuf-perlxs], [0.1], [dave@daveb.net])
AM_INIT_AUTOMAKE([-Wall])
AC_PROG_CXX
AC_PROG_CC
AC_PROG_INSTALL

dnl Look for protobuf headers and libs

AC_ARG_WITH(protobuf,
[  --with-protobuf[=DIR]     where to find Google's Protocol Buffers],,
  with_protobuf=yes)

if test "$with_protobuf" != no; then
  if test -d "$with_protobuf"; then
    CPPFLAGS="$CPPFLAGS -I$with_protobuf/include"
    LDFLAGS="$LDFLAGS -L$with_protobuf/lib"
  else
    AC_CHECK_HEADER(google/protobuf/stubs/common.h,,
    [AC_MSG_ERROR([protobuf headers are required.  Try using the --with-protobuf option.])])
  fi
fi

AC_CONFIG_FILES([
Makefile
src/Makefile
examples/Makefile.PL
])
AC_OUTPUT
