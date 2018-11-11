Carla Simulator
===============

About
-----

Carla is an open source, autonomous vehicle simulator built on the Unreal Game
Engine. When run, the Carla game/physics-engine application acts as a server to
which a Python client can be connected to gather sensor data and drive the
vehicle.

Useful links:
  - Webpage - `<http://carla.org/>`_
  - Docs - `<https://carla.readthedocs.io/en/stable/>`_
  - GitHub - `<https://github.com/carla-simulator/carla/>`_

Relevant papers:
  - [1] A. Dosovitskiy, G. Ros, F. Codevilla, A. Lopez, and V. Koltun,
    “CARLA: An Open Urban Driving Simulator,”
    `arXiv:1711.03938 <https://arxiv.org/abs/1711.03938>`_ [cs], Nov. 2017.

.. warning::
  - To access Epic’s marketplace to download community environments or assets,
    Windows OS is required
  - Building on Windows allows compatibility with Linux, but not vice versa
  - You **HAVE TO** use **Carla 0.8.2 on Unreal Engine 4.18** for successfully
    building the project and using the PythonAPI
  - Building/packaging an Unreal project takes a long time
