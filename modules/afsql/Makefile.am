moduledir = @moduledir@
AM_CPPFLAGS = -I$(top_srcdir)/lib -I../../lib
export top_srcdir

if ENABLE_SQL

module_LTLIBRARIES := libafsql.la
libafsql_la_SOURCES = \
	afsql.c afsql.h \
	afsql-grammar.y afsql-parser.c afsql-parser.h afsql-plugin.c

libafsql_la_CPPFLAGS = $(AM_CPPFLAGS) -DENABLE_SQL=1
libafsql_la_LIBADD = $(MODULE_DEPS_LIBS) $(LIBDBI_LIBS) $(OPENSSL_LIBS)
libafsql_la_LDFLAGS = $(MODULE_LDFLAGS)

endif

BUILT_SOURCES = afsql-grammar.y afsql-grammar.c afsql-grammar.h
EXTRA_DIST = $(BUILT_SOURCES) afsql-grammar.ym

include $(top_srcdir)/build/lex-rules.am
