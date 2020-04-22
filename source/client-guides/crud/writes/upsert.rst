An **upsert** is a write operation that either inserts a new object with a given
primary key or updates an existing object that already has that primary key. We
call this an upsert because it is an "**update** or **insert**" operation. This
is useful when an object may or may not already exist, such as when bulk
importing a dataset into an existing {+realm+}. Upserting is an elegant way to
update existing entries while adding any new entries.
