:term:`{+client-database+}` uses a highly efficient storage engine
to persist objects. You can **create** objects in a :term:`{+realm+}`,
**update** objects in a {+realm+}, and eventually **delete**
objects from a {+realm+}. Because these operations modify the
state of the {+realm+}, we call them writes.

{+client-database+} handles writes in terms of **transactions**. A
transaction is a list of read and write operations that
{+client-database+} treats as a single indivisable operation. In other
words, a transaction is *all or nothing*: either all of the
operations in the transaction succeed or none of the
operations in the transaction take effect.

.. admonition:: Remember
   :class: note

   All writes must happen in a transaction.

A {+realm+} allows only one open transaction at a time. {+client-database+}
blocks other writes on other threads until the open
transaction is complete. Consequently, there is no race
condition when reading values from the {+realm+} within a
transaction.

When you are done with your transaction, {+client-database+} either
**commits** it or **cancels** it:

- When {+client-database+} **commits** a transaction, {+client-database+} writes
  all changes to disk. For :term:`synced {+realms+} <{+sync+}>`,
  {+client-database+} queues the change for synchronization with
  :term:`{+service+}`.

- When {+client-database+} **cancels** a write transaction or an operation in
  the transaction causes an error, all changes are discarded
  (or "rolled back").
