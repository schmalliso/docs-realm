{+client-database+} represents each transaction as a callback function that
contains zero or more read and write operations. To run a transaction, define a
transaction callback and pass it to the {+realm+}'s ``write`` method. Within
this callback, you are free to create, read, update, and delete on the
{+realm+}. If the code in the callback throws an exception when
{+client-database+} runs it, {+client-database+} cancels the transaction.
Otherwise, {+client-database+} commits the transaction immediately after the
callback.

.. admonition:: Concurrency Concerns
   :class: important

   Since transactions block each other, it is best to avoid opening transactions
   on both the UI thread and a background thread. If you are using :doc:`Sync
   </sync/sync-overview>`, avoid opening transactions on the UI thread
   altogether, as {+client-database+} processes synchronizations on a background
   thread. If a background transaction blocks your UI thread's transaction, your
   app may appear unresponsive.
