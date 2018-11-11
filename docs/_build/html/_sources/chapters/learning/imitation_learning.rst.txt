Imitation Learning
===================

Carla has provided trained end-to-end imitation learning model code on their
`GitHub IL repository <https://github.com/carla-simulator/imitation-learning>`_.

Prerequisites
-------------

- Ubuntu 16.04
- Carla
- Python 3

Setup
--------

1. Ensure that Carla is running as expected.

2. Go to the ``PythonClient`` directory and clone the imitation learning code:

   .. code-block:: bash

      git clone https://github.com/carla-simulator/imitation-learning.git

3. The Imitation Learning code uses `TensorFlow <https://www.tensorflow.org/>`_.
   Installation instructions can be found on the `official documentation
   <https://www.tensorflow.org/install/>`_, or run the following commands:

   .. code-block:: bash

      sudo apt update
      sudo apt install python3-dev python3-pip

      pip3 install tensorflow-gpu --user # for gpu version
      pip3 install tensorflow --user # for cpu version (choose only one!)

.. note:: The Imitation Learning code was tested on TensorFlow version 1.4.0,
          but other versions should be compatible as well.

4. Test your TensorFlow installation before proceeding. Run ``python3`` and then:

   .. code-block:: python

      import tensorflow

If no errors pop up, go ahead with the next step. Otherwise, lookup the error
message on the internet for possible solutions. Note that most issues with
TensorFlow installations happen due to issues with CUDA and cuDNN libraries and
version mismatch.

5. One terminal one, run the carla server as decribed before:

   .. code-block:: bash

      ./CarlaUE4.sh -carla-server /Game/Maps/Town02 -benchmark -fps=10 -windowed -ResX=800 -ResY=600

6. On the other terminal run the following command:

   .. code-block:: bash

      python3 PythonClient/imitation-learning/run_CIL.py -c Town02

If all goes, well, this command will go thorough all the scenarios described in
the benchmark file (``PythonClient/carla/driving_benchmark/experiment_suites/corl_2017.py``).
The poses mentioned in the ``corl_2017.py`` file refer to an array of various
starting and ending positions of the car. These positions can be visualized by
running the ``view_start_positions.py`` file.

References:
-----------

- [1] F. Codevilla, M. Müller, A. López, V. Koltun, and A. Dosovitskiy,
  “End-to-end Driving via Conditional Imitation Learning,”
  `arXiv:1710.02410 <https://arxiv.org/abs/1710.02410>`_
  [cs], Oct. 2017.
