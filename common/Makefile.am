if !ENABLE_TRANSPARENCY
themedir        = $(datadir)/themes/Gruv-solid
else
themedir        = $(datadir)/themes/Gruv
endif

ithemedir       = $(DESTDIR)$(themedir)

install-exec-hook:

install-data-local:

if ENABLE_GRUV
	$(MKDIR_P) 
	
    cp $(srcdir)/index.theme $(ithemedir)
endif

# ENABLE_GNOME_SHELL
if ENABLE_GNOME_SHELL
	$(MKDIR_P) $(ithemedir)/gnome-shell

	cd $(srcdir)/gnome-shell/$(GNOME_VERSION) && cp -R \
		common-assets \
		light-assets \
		gnome-shell.css \
		$(ithemedir)/gnome-shell

endif # ENABLE_GNOME_SHELL

if ENABLE_GTK3
if ENABLE_GRUV
	$(MKDIR_P) $(ithemedir)/gtk-3.0

	cd $(srcdir)/gtk-3.0 && cp thumbnail.png $(ithemedir)/gtk-3.0

	cd $(srcdir)/gtk-3.0/$(GNOME_VERSION) && cp -R \
		assets \
		gtk.css \
		$(ithemedir)/gtk-3.0
endif

if !ENABLE_TRANSPARENCY
if ENABLE_GRUV
	cd $(srcdir)/gtk-3.0/$(GNOME_VERSION) && cp -R \
		gtk-solid.css \
		$(ithemedir)/gtk-3.0/gtk.css
endif
endif #!ENABLE_TRANSPARENCY
endif # ENABLE_GTK3

if ENABLE_XFWM
if ENABLE_GRUV
	$(MKDIR_P) $(ithemedir)/xfwm4

	cd $(srcdir)/xfwm4 && \
		cp -R assets/*.png $(ithemedir)/xfwm4 && \
		cp themerc $(ithemedir)/xfwm4/themerc
endif # ENABLE_LIGHT
endif # ENABLE_XFWM


uninstall-local:
	rm -rf $(ithemedir)

EXTRA_DIST = $(srcdir)/gnome-shell \
	     $(srcdir)/gtk-3.0 \
	     $(srcdir)/xfwm4 \
	     $(srcdir)/index.theme
