.. _targetRes: 

targetRes
=========

.. currentmodule::  apbs.input_file.calculate.finite_element

.. note::
   
   This command has been ported to the *new APBS syntax* (see :ref:`new_input_format`); see :func:`FiniteElement.initial_mesh_resolution`.

Specify the target resolution of the simplices in a finite element mesh (:ref:`femanual`).
The syntax is:

.. code-block:: bash
   
   targetRes { res }

where ``res`` is a floating point number denoting the target resolution for longest edges of simplices in mesh (in Å).
Refinement will continue until the longest edge of every simplex is below this value or the number of vertices reaches :ref:`targetNum`.
