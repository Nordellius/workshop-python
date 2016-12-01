*********
Iteratory
*********

Czym jest iterator?
===================

* ``__next__()``
* ``raise StopIteration``

Iterowanie po obiektach
=======================

Iterowanie po stringu
---------------------

.. code-block:: python

    for znak in 'python':
        print(znak)


Iterowanie po ``list()``, ``dict()``, ``set()``, ``tuple()``
------------------------------------------------------------

.. code-block:: python

    for liczba in [1, 2, 3, 4]:
        print(liczba)

.. code-block:: python

    for key, value in [(0, 0), (1, 1), (1, 2)]:
        print('%s -> %s' % (key, value))

.. code-block:: python

    slownik = {'x': 1, 'y': 2}

    for key in slownik:
        print(slownik.get(key))

    for key, value in slownik.items():
        print(key, value)

Własny iterator
===============

.. code-block:: python

    class ListaFigurGeometrycznych:
        lista = []
        aktualny_elemtent = 0

        def __iter__(self):
            return self

        def push(self, figura):
            self.lista.append(figura)

        def next(self):
            self.aktualny_elemtent += 1
            return self.lista[self.aktualny_elemtent]

    prostokaty = ListaFigurGeometrycznych()
    prostokaty.push('kwadrat', 'prostokat')

    for figura in prostokaty:
        print(figura)
