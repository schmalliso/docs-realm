{+client-database+} guarantees that transactions are :term:`ACID` compliant.
This means that all committed write operations are guaranteed to be valid and
that clients don't see transient states in the event of a system crash.

- {+client-database+} establishes :wikipedia:`atomicity
  <Atomicity_(database_systems)>` by grouping operations in transactions and
  rolling back all operations in a transaction if any of them fail.

- {+client-database+} establishes :wikipedia:`consistency
  <Consistency_(database_systems)>` and avoids data corruption by validating
  changes against the schema. If the result of any write operation is not valid,
  {+client-database+} cancels and rolls back the entire transaction.

- {+client-database+} establishes :wikipedia:`isolation
  <Isolation_(database_systems)>` by allowing only one writer at a time. This
  ensures thread safety between transactions.

- Finally, {+client-database+} establishes :wikipedia:`durability
  <Durability_(database_systems)>` by writing to disk immediately when a
  transaction is committed. In the event of an app crash, for example, the
  changes are not lost or corrupted.
