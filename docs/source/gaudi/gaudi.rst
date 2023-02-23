=====================
Diving into ``Gaudi``
=====================

    :Author: yong

.. contents::



0.1 Plugin Service and Factory
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

0.2 Value Semantics and Ownership Management
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Basically, it's like shared pointer implementation to manage the underlying resources.

0.2.1 idoms
^^^^^^^^^^^

0.2.1.1 copy-swap and copy-elison
:::::::::::::::::::::::::::::::::

For copy assignment, copy-swap avoids the self-assignment bug and provides better exception
safety.
**copy-elison** (i.e. pass-by-value style assignment in this case) further improves the
performances in cases where rvalue on the right side.

See:

- `More C++ Idioms wikibook <https://en.wikibooks.org/wiki/More_C%2B%2B_Idioms/Copy-and-swap>`_

- podio ObjBase implementation

- boost shared\_ptr implementation

0.2.1.2 reference-counting
::::::::::::::::::::::::::

See:

- `The example is almost the same as podio's data model implementation <https://en.wikibooks.org/wiki/More_C%2B%2B_Idioms/Counted_Body>`_

0.2.1.3 handle-body (AKA: pointer to implementation)
::::::::::::::::::::::::::::::::::::::::::::::::::::

See the previous section's link.

0.3 Parallelism
~~~~~~~~~~~~~~~

0.3.1 Multi-Process
^^^^^^^^^^^^^^^^^^^

0.3.2 Multi-Thread
^^^^^^^^^^^^^^^^^^

0.3.3 Multi-Job
^^^^^^^^^^^^^^^

0.3.4 Multi-Node??
^^^^^^^^^^^^^^^^^^

0.4 Finite State Machine (FSM)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

0.5 Curiously Recurring Template Pattern (CRTP)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

1 Implementation
----------------

1.1 Concurrency
~~~~~~~~~~~~~~~

1.1.1 GaudiHive (MT)
^^^^^^^^^^^^^^^^^^^^

1.1.2 GaudiMP (MP)
^^^^^^^^^^^^^^^^^^

1.2 Interface
~~~~~~~~~~~~~

1.2.1 IService
^^^^^^^^^^^^^^

1.2.2 IProperty
^^^^^^^^^^^^^^^

1.2.3 ITool
^^^^^^^^^^^

1.2.4 IStateful
^^^^^^^^^^^^^^^

2 Modernization Effort
----------------------

2.1 overview
~~~~~~~~~~~~

`Gaudi Evolution for Future Chanllege <https://iopscience.iop.org/article/10.1088/1742-6596/898/4/042044>`_

- Task-based, intra-event parallelization: GaudiHive

- Reentrant Algorithm

  - A subset: Gaudi\:\:Functional framework

- 

2.2 Config2
~~~~~~~~~~~

`~/src/physics/key4hep/Gaudi/GaudiConfiguration/doc/README.md <~/src/physics/key4hep/Gaudi/GaudiConfiguration/doc/README.md>`_

2.3 Histogram
~~~~~~~~~~~~~

`see this commit <https://gitlab.cern.ch/gaudi/Gaudi/-/merge_requests/1113/diffs#f623fa84d5ad96cef7c3cc45409a10f418592ad7>`_

3 Integration into downstream project
-------------------------------------

3.1 As separate external installation
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

3.1.1 View-based version control?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

3.1.2 A package stack installation script which provides a view
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

3.2 As internal sub-project
~~~~~~~~~~~~~~~~~~~~~~~~~~~

3.2.1 cmake external project?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
