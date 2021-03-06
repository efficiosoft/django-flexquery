django-flexquery
================

.. toctree::
   :glob:
   :hidden:

   Introduction <self>
   q
   flexquery
   contrib/*

This library aims to provide a new way of declaring reusable QuerySet filtering
logic in your Django project, incorporating the DRY principle and maximizing user
experience and performance by allowing you to decide between sub-queries and JOINs.

Its strengths are, among others:

* Easy to learn in minutes
* Cleanly integrates with Django's ORM
* Small code footprint, hard for bugs to hide - ~150 lines of code (LoC)
* 100% test coverage
* Fully documented code, formatted using the excellent `Black Code Formatter
  <https://github.com/python/black>`_.

When referencing a related model in a database query, you usually have the choice
between using a JOIN (``X.objects.filter(y__z=2)``) or performing a sub-query
(``X.objects.filter(y__in=Y.objects.filter(z=2))``).

We don't want to judge which one is better, because that depends on the concrete
query and how the database engine in use optimizes it. In many cases, it will hardly
make a noticeable difference at all. However, when the amount of data grows, doing
queries right can save you and the users of your application several seconds, and
that is what django-flexquery is for.


Requirements
------------

Continuous integration ensures compatibility with Python 3.7 + Django 2.2 and 3.0.


Installation
------------

::

    pip install django-flexquery

No changes to your Django settings are required; no ``INSTALLED_APPS``, no
``MIDDLEWARE_CLASSES``.
