AC_PREREQ(2.52)

AC_INIT([apertium-kaz-tyv], [0.2.0], [francis.tyers@uit.no])
AM_INIT_AUTOMAKE([apertium-kaz-tyv], [0.2.0], no-define)
AC_PROG_LN_S
AC_PROG_AWK

m4_define([required_apertium_version], [3.3.0])
PKG_CHECK_MODULES(APERTIUM, apertium >= required_apertium_version, [], [PKG_CHECK_MODULES(APERTIUM, apertium-3.2 >= required_apertium_version)])


AC_PATH_PROG(HFSTLEXC, hfst-lexc, no)
if test x$ac_cv_path_HFSTLEXC = x
then
  AC_MSG_ERROR([You don't have hfst-lexc installed.])
fi
if test x$ac_cv_path_HFSTLEXC = xno
then
  AC_MSG_ERROR([You don't have hfst-lexc installed.])
fi

AC_PATH_PROG(HFSTTWOLC, hfst-twolc, no)
if test x$ac_cv_path_HFSTTWOLC = x
then
  AC_MSG_ERROR([You don't have hfst-twolc installed.])
fi
if test x$ac_cv_path_HFSTTWOLC = xno
then
  AC_MSG_ERROR([You don't have hfst-twolc installed.])
fi

AC_PATH_PROG(CGCOMP, cg-comp, no)
if test x$ac_cv_path_CGCOMP = x
then
  AC_MSG_ERROR([You don't have cg-comp installed.])
fi
if test x$ac_cv_path_CGCOMP = xno
then
  AC_MSG_ERROR([You don't have cg-comp installed.])
fi

AC_PATH_PROG(CGPROC, cg-proc, no)
if test x$ac_cv_path_CGPROC = x
then
  AC_MSG_ERROR([You don't have cg-proc installed.])
fi
if test x$ac_cv_path_CGPROC = xno
then
  AC_MSG_ERROR([You don't have cg-proc installed.])
fi

AC_PATH_PROG(LRXCOMP, lrx-comp, no)
if test x$ac_cv_path_LRXCOMP = x
then
  AC_MSG_ERROR([You don't have lrx-comp installed.])
fi
if test x$ac_cv_path_LRXCOMP = xno
then
  AC_MSG_ERROR([You don't have lrx-comp installed.])
fi

AC_PATH_PROG(LRXPROC, lrx-proc, no)
if test x$ac_cv_path_LRXPROC = x
then
  AC_MSG_ERROR([You don't have lrx-proc installed.])
fi
if test x$ac_cv_path_LRXPROC = xno
then
  AC_MSG_ERROR([You don't have lrx-proc installed.])
fi

AC_PATH_PROG(GZCAT, gzcat, no)
AC_PATH_PROG(ZCAT, zcat, no)

if test x$ac_cv_path_GZCAT = xno
then
  if test x$ac_cv_path_ZCAT = xno
  then
    AC_MSG_ERROR([No working zcat installed.])
  else
    AC_SUBST(ZCAT,[zcat])
  fi
else
  AC_SUBST(ZCAT,[gzcat])
fi

m4_ifdef([AP_CHECK_LING],[],[AC_MSG_ERROR([AP_CHECK_LING not defined, is apertium.m4 in ACLOCAL_PATH? See: https://wiki.apertium.org/wiki/Installation_troubleshooting])])

AP_CHECK_LING([1], [apertium-kaz])
AP_CHECK_LING([2], [apertium-tyv])

PKG_CHECK_MODULES(REGTEST, apertium-regtest >= 0.0.1, [],
                  [AC_MSG_WARN([Running tests requires apertium-regtest])])

AP_MKINCLUDE

AC_OUTPUT([Makefile])

