OMERO Service Example
=====================
Open Microscopy Environment service template for extending server functionality.

Requirements
============

* OMERO 4.4.0 or later

Installation
============

Clone the repository in to your tools directory:

    cd openmicroscopy.git
    git clone git://github.com/openmicroscopy/ome-services-example components/tootls/MyService
    ./build.py

Now start up OMERO as normal and your service will be available.

Example usages
==============

A frequent request is the addition of a custom LDAP implementation. For this,
there must be an implementation of ome.security.auth.NewUserGroupBean present
under src and a Spring configuration file instantiating this concrete class
under resources. To configure the bean in your server:

    cd OMERO_DIST
    bin/omero config set omero.ldap.new_user_group :bean:myNewUserGroupMapperBean
    bin/omero admin restart

See http://trac.openmicroscopy.org/ome/wiki/ExtendingOmero for more information.
