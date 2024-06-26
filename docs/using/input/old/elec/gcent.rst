.. _gcent:

gcent
======

.. currentmodule::  apbs.input_file.calculate.finite_difference

.. note::  This command has been ported to the *new APBS syntax* (see :ref:`new_input_format`); see :class:`GridCenter` for more information.

Specify the center of the grid based on a molecule's center or absolute coordinates :ref:`mgmanual` multigrid calculations.
The syntax is:

.. code-block:: bash
   
   fgcent { mol id | xcent ycent zcent }

where a user can specify **either**

``mol {id}``
  Center the grid on molecule with integer ID id; as assigned in the READ section (see :ref:`read_old_input`) of the input file.
  Molecule IDs are assigned in the order they are read, starting at 1.

**or** the user can specify

``xcent ycent zcent``
  Center the grids on the coordinates (floating point numbers in Å) at which the grid is centered.
  Based on the input molecule PDB coordinate frame.

