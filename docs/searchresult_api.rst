====================
``SearchResult`` API
====================

The ``SearchResult`` class provides structure to the results that come back from
the search index. These objects are what a ``SearchQuerySet`` will return when
evaluated.


Attribute Reference
===================

The class exposes the following useful attributes/properties:

* ``app_label`` - The application the model is attached to.
* ``model_name`` - The model's name.
* ``pk`` - The primary key of the model.
* ``score`` - The score provided by the search engine.
* ``object`` - The actual model instance (lazy loaded).
* ``model`` - The model class.
* ``verbose_name`` - A prettier version of the model's class name for display.


Method Reference
================

``content_type(self)``
----------------------

Returns the content type for the result's model instance.

``get_additional_fields(self)``
-------------------------------

Returns a dictionary of all of the fields from the raw result.

Useful for serializing results. Only returns what was seen from the
search engine, so it may have extra fields Haystack's indexes aren't
aware of.

``get_stored_fields(self)``
---------------------------

Returns a dictionary of all of the stored fields from the SearchIndex.

Useful for serializing results. Only returns the fields Haystack's
indexes are aware of as being 'stored'.
