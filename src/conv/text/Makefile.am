if BUILD_TOOLS

bin_PROGRAMS = pmd2text

AM_CXXFLAGS = -I$(top_srcdir)/inc $(REVENGE_CFLAGS) $(REVENGE_GENERATORS_CFLAGS) $(REVENGE_STREAM_CFLAGS) $(DEBUG_CXXFLAGS)

pmd2text_DEPENDENCIES = @PMD2RAW_WIN32_RESOURCE@

pmd2text_LDADD = ../../lib/libpagemaker-@PMD_MAJOR_VERSION@.@PMD_MINOR_VERSION@.la $(REVENGE_LIBS) $(REVENGE_GENERATORS_LIBS) $(REVENGE_STREAM_LIBS) @PMD2RAW_WIN32_RESOURCE@

pmd2text_SOURCES = \
	pmd2text.cpp

if OS_WIN32

@PMD2RAW_WIN32_RESOURCE@ : pmd2text.rc $(pmd2text_OBJECTS)
	chmod +x $(top_srcdir)/build/win32/*compile-resource
	WINDRES=@WINDRES@ $(top_srcdir)/build/win32/lt-compile-resource pmd2text.rc @PMD2RAW_WIN32_RESOURCE@
endif

EXTRA_DIST = \
	$(pmd2text_SOURCES) \
	pmd2text.rc.in

# These may be in the builddir too
BUILD_EXTRA_DIST = \
	pmd2text.rc

endif
