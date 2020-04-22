Sometimes, you have :doc:`dependent objects </data-model/relationships>` that
you want to delete when you delete the parent object. We call this a **cascading
delete**. {+client-database+} will not delete the dependent objects for you. If
you do not delete the objects yourself, they will remain orphaned in your
{+realm+}. Whether or not this is a problem depends on your application's needs.

Currently, the best way to delete dependent objects is to iterate through the
dependencies and delete them before deleting the parent object.
