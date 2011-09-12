Django Email Registration
=========================

This is a fork of James Bennett's django-registration, redesigned
to support email registrations as first-class citizens in Django.

This is currently very beta software; there's a good chance the API may change.

Dependencies
-----------

* Only tested on Django 1.3

Assumptions
-----------

This package goes against some of the established Django practices;
it may be helpful to summarize any pitfalls.

* Email is a first-class citizen for authentication
* Email is unique and case-insensitive for each User
* Username is unique and case-insensitive for each User
* Modify Django internals and assumptions as little as possible
* If a username is optional, autogenerate it: does not hurt the Users (who can't see it),
  and it plays nicely with other applications and Django internals


Installation
------------

TODO!

* This is currently not packaged proper. For now you need to clone the repo
  and add it your PYTHON_PATH (e.g. myproject/vendor/django-email-registration).
* Add to INSTALLED_APPS
* Migrate Database (unique index constraint on email)


Development
------------

Requirements: pip + virtualenv + virtualenvwrapper

I've included a basic testapp in order to test the package in isolation:

    $ mkvirtualenv djreg
    $ git clone https://github.com/pithyless/django-email-registration.git
    $ cd django-email-registration
    $ pip install -r testapp/requirements.txt

    $ echo "export DJANGO_SETTINGS_MODULE=settings" >> $VIRTUAL_ENV/bin/postactivate
    $ echo "unset DJANGO_SETTINGS_MODULE" >> $VIRTUAL_ENV/bin/postdeactivate
    $ add2virtualenv /path/to/django-email-registration
    $ add2virtualenv /path/to/django-email-registration/testapp

    $ django-admin.py syncdb
    $ django-admin.py test
