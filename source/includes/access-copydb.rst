.. target-non-admin-source

If the source database is not the ``admin`` database, you must
have privileges that specify :authaction:`insert` and
:authaction:`createIndex` actions on the target database, and
:authaction:`insert` action on the ``system.js`` collection in the
target database. For example:

.. code-block:: javascript

   { resource: { db: "myTargetDB", collection: "" }, actions: [ "insert", "createIndex" ] }
   { resource: { db: "myTargetDB", collection: "system.js" }, actions: [ "insert" ] }

.. target-admin-source

If the source database is the ``admin`` database, you must have
privileges that specify :authaction:`insert` and
:authaction:`createIndex` actions on the target database, and
:authaction:`insert` action on the ``system.js``, ``system.users``,
``system.roles``, and ``system.version`` collections in the target
database. For example:

.. code-block:: javascript

   { resource: { db: "myTargetDB", collection: "" }, actions: [ "insert", "createIndex" ] },
   { resource: { db: "myTargetDB", collection: "system.js" }, actions: [ "insert" ] },
   { resource: { db: "myTargetDB", collection: "system.users" }, actions: [ "insert" ] },
   { resource: { db: "myTargetDB", collection: "system.roles" }, actions: [ "insert" ] },
   { resource: { db: "myTargetDB", collection: "system.version" }, actions: [ "insert" ] }

.. source-not-admin

If the source database is a non-``admin`` database, you must have
privileges that specify :authaction:`find`, :authaction:`listCollections`,
and :authaction:`listIndexes` actions on the source database, and
:authaction:`find` action on the ``system.js`` collection in the
source database. For example:

.. code-block:: javascript

   { resource: { db: "mySourceDB", collection: "" }, actions: [ "find", "listCollections", "listIndexes" ] }
   { resource: { db: "mySourceDB", collection: "system.js" }, actions: [ "find" ] }

.. source-admin

If the source database is the ``admin`` database, you must have
privileges that specify :authaction:`find`, :authaction:`listCollections`,
and :authaction:`listIndexes`  actions on the ``admin``
database, and :authaction:`find` action on the ``system.js``,
``system.users``, ``system.roles``, and ``system.version`` collections
in the ``admin`` database. For example:

.. code-block:: javascript

   { resource: { db: "admin", collection: "" }, actions: [ "find",  "listCollections", "listIndexes" ] }
   { resource: { db: "admin", collection: "system.js" }, actions: [ "find" ] }
   { resource: { db: "admin", collection: "system.users" }, actions: [ "find" ] }
   { resource: { db: "admin", collection: "system.roles" }, actions: [ "find" ] }
   { resource: { db: "admin", collection: "system.version" }, actions: [ "find" ] }
