AC_INIT([Guile-Yamlpp], [0.1])

AC_CONFIG_AUX_DIR([build-aux])
AM_INIT_AUTOMAKE([color-tests parallel-tests -Wall -Werror foreign])

GUILE_PKG([3.0])
GUILE_PROGS
if test "x$GUILD" = "x"; then
   AC_MSG_ERROR(['guild' binary not found; please check your guile-3.x installation.])
fi

AC_CONFIG_FILES([Makefile])
AC_CONFIG_FILES([pre-inst-env], [chmod +x pre-inst-env])

dnl Installation directories for .scm and .go files.
gloa_prefix="`eval echo $prefix | sed -e"s|NONE|/usr/local|g"`"
gloa_libdir="`eval echo $libdir | sed -e"s|NONE|$gloa_prefix|g"`"
guilemoduledir="`eval echo ${datarootdir}/guile/site/$GUILE_EFFECTIVE_VERSION | sed -e "s|NONE|$gloa_prefix|g"`"
guileobjectdir="`eval echo ${libdir}/guile/$GUILE_EFFECTIVE_VERSION/site-ccache | sed -e "s|NONE|$gloa_prefix|g"`"
AC_SUBST([guilemoduledir])
AC_SUBST([guileobjectdir])

AC_OUTPUT
