Choosing a Simulator
========================

Comparison
-----------

Different simulators were tested to decide which one(s) would be most relavant
to our project.

.. figure:: ../data/simulators.gif
   :align: center

   Some simulators in action

Comparison of different simulators:

.. csv-table:: Table 1: Comparison of Autonomous Simulators
   :file: ../data/table01_08-04-2018.csv
   :header-rows: 1

Common notes:
  - All simulators require dedicated GPU
  - Their usage is not always trivial
  - SITL: Software in the Loop
  - Since our objective is for testing in a simulation environment,
    hardware focused simulators have been given a negative weightage

Knowlegde prerequisites:
  - Linux
  - Python
  - GitHub
  - Docker (Apollo only)
  - Machine Learning Practices

Selection
---------
In the end, after testing the simulators, **Carla** was chosen to be the
primary autonomous simulator for the project, because it had good documentation,
was the easy to set-up, and already came with end-to-end learning code.
