In general, to delete an object from a {+realm+}, pass the instance to the
delete method of the {+realm+} within a transaction.

.. admonition:: Do not use objects after delete
   :class: important

   {+client-database+} throws an error if you try to use an object after it has
   been deleted.
