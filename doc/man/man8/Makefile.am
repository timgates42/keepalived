# Makefile.am
#
# Keepalived OpenSource project.
#
# Copyright (C) 2001-2017 Alexandre Cassen, <acassen@gmail.com>

DATE=`date --date=\"\`git log -n 1 -- $@.in | grep Date: | sed -e \"s/  */ /g\" | cut -d' ' -f 4,3,6\`\" +\"%Y-%m-%d\"`

edit = echo "  EDIT     $@"; \
	sed \
	 -e 's|@DEFAULT_CONFIG_FILE[@]|$(DEFAULT_CONFIG_FILE)|g' \
	 -e "s|@DATE[@]|$(DATE)|g"

dist_man8_MANS  = keepalived.8

keepalived.8: Makefile
	@$(edit) '$(srcdir)/$@.in' >$@

keepalived.8: $(srcdir)/keepalived.8.in

EXTRA_DIST		= keepalived.8.in

MOSTLYCLEANFILES	= keepalived.8
