0.0.6
=====

Fix a problem where repointing a deferred foreign key defined on a non-abstract
base class through a subclass would result in a new field being added to the
local_fields of the subclass, shadowing the one on the base class. It is now
illegal to do this; dfks on base classes should be pointed using the base class
itself.

0.0.5
=====

Fix a problem where related object caches on models' _meta Options classes
were not being repopulated on a repoint. This led to problems where
filtering on a parent model related to a child using a deferred foreign key
could fail if the dfk was (re)pointed after the initial phase of model loading
had already taken place.

0.0.4
=====

- Include a MANIFEST.in to ensure docs are packaged.

0.0.3
=====
- Fix packaging error

0.0.2
=====

- Fix an issue when repointing foreign keys on model classes with custom
  fields which use the django.db.models.SubfieldBase metaclass
- Fix an issue migrating from Django 1.2 to 1.3.

0.0.1
=====

- Initial version