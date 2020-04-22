Results to a query are not copies of your data: modifying the results of a query
will modify the data on disk directly. This memory mapping also means that
results are **live**: that is, they always reflect the current state on disk.

See also: :ref:`Collections are Live <live-collections>`.
