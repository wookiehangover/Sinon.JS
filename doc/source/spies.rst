Test spies
==========

A test spy is a function that wraps another function. Whenever the spy is
called, it records the +this+ value, received arguments, return value and
possible exceptions. Test spies also record meta data such as the number of
calls as well as a call id which can be used to determine call order. The spy
acts exactly as the wrapped function and the wrapped function will not behave
differently when wrapped.

Test spies expose a rich API to inspect meta data related to calls. Sinon stubs
and mocks are also test spies.

.. js:function:: sinon.spy()

   :returns: An anonymous spy function

.. js:function:: sinon.spy(fn)

   :param function fn: A function to spy on
   :returns: A spy function that behaves exactly like the original function

You can also pass a method to the +sinon.spy+ method. By assigning the spy back
to the object, the method will behave as expected (i.e. with correct `this`
value and so on).

.. [source,javascript]
.. ----
.. var person = {
..   name: "Christian",

..   getName: function () {
..     return name;
..   }
.. };

.. person.getName = sinon.spy(person.getName);
.. ----

Even though the above example works on methods, Sinon offers another way to spy
on methods which allows you to un-spy at a later point.

.. js:function:: sinon.spy(obj, fn)

   :param object obj: An object
   :param string fn: Name of a function property on obj on which to spy
   :returns: A spy function that behaves exactly like the original function

.. [source,javascript]
.. ----
.. var person = {
..   name: "Christian",

..   getName: function () {
..     return name;
..   }
.. };

.. sinon.spy(person, "getName");
.. // ...
.. person.getName.restore(); // Restores the original method
.. ----

Overrides the original property with a spy function that wraps and behaves
exactly like the original method. The spy gains a :js:function:`restore` method
which causes the original function to be restored on the object.

.. .. js:function:: enumerate(sequence[, start=0])

..    :param string href: An URI to the location of the resource.
..    :param callback: Get's called with the object.
..    :param errback:
..        Get's called in case the request fails. And a lot of other
..        text so we need multiple lines
..    :throws SomeError: For whatever reason in that case.
..    :returns: Something

..    Return an iterator that yields tuples of an index and an item of the
..    *sequence*. (And so on.)
