In general, instantiate :doc:`{+service-short+} objects </data-model/objects>`
as you would any other object. In a transaction, you can add the object to the
{+realm+} if the {+realm+}'s :ref:`schema <realm-schema>` includes the object
type. When you add an instance to the {+realm+}, it becomes *managed* by that
{+realm+}.

With the Java and JavaScript SDKs, instead use the {+realm+}'s factory method in
a transaction to instantiate your class. This automatically inserts the instance
into the {+realm+}.
