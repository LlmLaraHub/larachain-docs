Overview
=====

The basic simple principle is getting the right "context" to give
a LLM prompt. This "context" comes from the query using https://github.com/pgvector/pgvector-php
Then adding a Prompt that does a good job of asking for a summary of that context based on the users question.

That is it!

On top of that the system is LLM agnostic.


Collections
----------------
Collections make up the "Chattable" grouping of Documents. You make a collection
and add documents to it.

Since this system uses Laravel JetStream https://jetstream.laravel.com/introduction.html
we can share those collections with others on the team.


Documents
----------------
This is the foundation to the searchable content. It can come from PDFs, Websites,
Power Points, Text and more.

When a document is added the system will do the following.

  * Break it into Chunks (small fragments) that overlap with the sibling before and after it.
  * Do vector embedding on it so we can query it later

Document Chunks
----------------
These are related to documents. They have the chunk of text from the document.
A page number and a sort number. This always has the vector field we do all the searching on.






To retrieve a list of random ingredients,
you can use the ``lumache.get_random_ingredients()`` function:

.. autofunction:: lumache.get_random_ingredients

The ``kind`` parameter should be either ``"meat"``, ``"fish"``,
or ``"veggies"``. Otherwise, :py:func:`lumache.get_random_ingredients`
will raise an exception.

.. autoexception:: lumache.InvalidKindError

For example:

>>> import lumache
>>> lumache.get_random_ingredients()
['shells', 'gorgonzola', 'parsley']

