Reinforcement Learning
========================

Carla has provided trained end-to-end reinforcement learning model code on their
 `GitHub RL repo <https://github.com/carla-simulator/reinforcement-learning>`_.

Prerequisites
-------------

- Ubuntu 16.04
- Carla
- Python 3

Setup
--------

1. Ensure that Carla is running as expected.

2. Go to the ``PythonClient`` directory and clone the reinforcement learning code:

  .. code-block:: bash

     git clone https://github.com/carla-simulator/reinforcement-learning.git

3. The Reinforcement Learning code uses `Chainer <https://chainer.org/>`_.
   Installation instructions can be found on the `official documentation
   <https://docs.chainer.org/en/stable/install.html/>`_, or run the following commands:

  .. code-block:: bash

     sudo apt update
     sudo apt install python3-dev python3-pip

     pip3 install chainer --user

.. note:: The Reinforcement Learning code was tested on Chainer version 4.3.1,
         but other versions should be compatible as well.

4. Test your Chainer installation before proceeding. Run ``python3`` and then:

  .. code-block:: python

     import chainer

If no errors pop up, go ahead with the next step. Otherwise, lookup the error
message on the internet for possible solutions.

For the error ``TypeError: __init__() got unexpected keyword argument(s) 'bias'``,

Change all ``L.Convolution2D`` params in the ``reinforcement-learning/agent/asyncrl/dqn_head.py``
file from:
```
L.Convolution2D(n_input_channels, 32, 8, stride=4, bias=bias),
```
to (base -> initial_bias)
```
L.Convolution2D(n_input_channels, 32, 8, stride=4, initial_bias=bias),
```

5. One terminal one, run the carla server as decribed before:

  .. code-block:: bash

     ./CarlaUE4.sh -carla-server /Game/Maps/Town02 -benchmark -fps=10 -windowed -ResX=800 -ResY=600

6. On the other terminal run the following command:

  .. code-block:: bash

     python3 PythonClient/reinforcement-learning/run_RL.py -c Town02

If all goes, well, this command will go thorough all the scenarios described in
the benchmark file (``PythonClient/carla/driving_benchmark/experiment_suites/corl_2017.py``).
The poses mentioned in the ``corl_2017.py`` file refer to an array of various
starting and ending positions of the car. These positions can be visualized by
running the ``view_start_positions.py`` file.

References:
-----------

- [1] A. Dosovitskiy, G. Ros, F. Codevilla, A. Lopez, and V. Koltun,
  “CARLA: An Open Urban Driving Simulator,”
  `arXiv:1711.03938 <https://arxiv.org/abs/1711.03938>`_ [cs], Nov. 2017.
