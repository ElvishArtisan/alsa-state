## automake.am
##
## Top level automake.am for alsa-state
##
## Use automake to process this into a Makefile.in
##
##   (C) Copyright 2014 Fred Gleason <fredg@paravelsystems.com>
##
##   This program is free software; you can redistribute it and/or modify
##   it under the terms of the GNU General Public License version 2 as
##   published by the Free Software Foundation.
##
##   This program is distributed in the hope that it will be useful,
##   but WITHOUT ANY WARRANTY; without even the implied warranty of
##   MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
##   GNU General Public License for more details.
##
##   You should have received a copy of the GNU General Public
##   License along with this program; if not, write to the Free Software
##   Foundation, Inc., 675 Mass Ave, Cambridge, MA 02139, USA.
##

rpm:	dist
	mkdir -p $(HOME)/rpmbuild/SOURCES
	cp alsa-state-$(VERSION).tar.gz $(HOME)/rpmbuild/SOURCES/
	$(RPMBUILD) -ba --target noarch-$(VENDOR)-linux alsa-state.spec
	mv $(HOME)/rpmbuild/RPMS/noarch/alsa-state-*.rpm $(top_srcdir)/
	mv $(HOME)/rpmbuild/SRPMS/alsa-state-*.src.rpm $(top_srcdir)/
	rm $(HOME)/rpmbuild/SOURCES/alsa-state-$(VERSION).tar.gz

EXTRA_DIST = autogen.sh\
             alsa-state.spec.in\
             rc.alsa-state

CLEANFILES = *~ *.tar.gz *.tgz *.mo *.rpm *.zip
DISTCLEANFILES = *.spec make_slack slack-desc
MAINTAINERCLEANFILES = *~ Makefile.in configure aclocal.m4 *.tar.gz\
                       config.guess config.status config.sub install-sh\
                       libtool ltmain.sh missing mkinstalldirs depcomp
