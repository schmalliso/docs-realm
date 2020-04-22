One benefit of {+client-database+}'s object model is that {+client-database+}
automatically retains all of an object's :doc:`relationships
</data-model/relationships>` as direct references, so you can traverse your
graph of relationships directly through the results of a query.

A **direct reference**, or pointer, allows you to access a related object's
properties directly through the reference.

Other databases typically copy objects from database storage into application
memory when you need to work with them directly. Because application objects
contain direct references, you are left with a choice: copy the object referred
to by each direct reference out of the database in case it's needed, or just
copy the foreign key for each object and query for the object with that key if
it's accessed. If you choose to copy referenced objects into application memory,
you can use up a lot of resources for objects that are never accessed, but if
you choose to only copy the foreign key, referenced object lookups can cause
your application to slow down.

{+client-database+} bypasses all of this using :term:`zero-copy` :term:`live
objects`. :term:`{+realm+} object` accessors point directly into database
storage using memory mapping, so there is no distinction between the objects in
{+client-database+} and the results of your query in application memory. Because
of this, you can traverse direct references across an entire {+realm+} from any
query result.
