include ../config.mak

APPDIRS=gpac

ifeq ($(MP4BOX_STATIC),yes)
APPDIRS+=mp4box 
else

ifeq ($(DISABLE_PLAYER), no)
APPDIRS+=mp4client 
endif

ifeq ($(DISABLE_ISOFF), no)
APPDIRS+=mp4box 

endif

V4STUDIODIR=
INSTDIRS=mp4client
ifeq ($(CONFIG_XUL),no)
else
#INSTDIRS+=osmozilla
#APPDIRS+=osmozilla
endif

#disable due to version incompatibilities
ifeq ($(USE_WXWIDGETS), yes)
#APPDIRS+=osmo4_wx
#V4STUDIODIR=V4Studio
#INSTDIRS+=osmo4_wx
endif

#MP4BOX_STATIC
endif

ALLDIRS=$(APPDIRS)

all: apps

apps: 
	set -e; for i in $(APPDIRS) ; do $(MAKE) -C $$i all; done 

sggen:
	$(MAKE) -C generators all

V4Studio:
	set -e; for i in $(V4STUDIODIR) ; do $(MAKE) -C $$i dep; done 

dep:
	set -e; for i in $(ALLDIRS) ; do $(MAKE) -C $$i dep; done 

clean: 
	set -e; for i in $(ALLDIRS) ; do $(MAKE) -C $$i clean; done 

distclean: 
	set -e; for i in $(ALLDIRS) ; do $(MAKE) -C $$i distclean; done 

install:
	set -e; for i in $(INSTDIRS) ; do $(MAKE) -C $$i install; done

uninstall:
	set -e; for i in $(INSTDIRS) ; do $(MAKE) -C $$i uninstall; done
	
