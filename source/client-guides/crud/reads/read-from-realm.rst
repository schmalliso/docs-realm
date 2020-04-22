A read from a :term:`{+realm+}` generally consists of the following steps:

- Get all :ref:`objects <realm-objects>` of a certain type from the {+realm+}.

- Optionally, :ref:`filter <filter-results>` the results using the :doc:`query
  engine </crud/query-engine>`.

- Optionally, |ref-sort-results| the results.

All query, filter, and sort operations return a :ref:`results collection
<results-collections>`. The results collections are live, meaning they always
contain the latest results of the associated query.
