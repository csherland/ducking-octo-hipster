ECE465-MatrixInversion
======================
Distributed matrix inversion project for ECE 465 - Cloud Computing at Cooper Union, Spring 2014.
Allows a client to specify a file of matrices to be proccessed by matrix inversion servers. Format
for input files is specified below, and script to generate test data is included in this repo.

Features an application layer load balancer to determine the best server for a client to connect to
for matrix inversion.

Contents
--------
The major components of this project can be divided into three parts - the matrix client, the load
balancer and the matrix inversion server. All of these are meant to run simultaneously and communicate
using network sockets. As such, these can all be run on one machine, or distributed across multiple
machines.

Usage
-----
In order to compile and run this project the general syntax is:

    mvn clean compile exec:exec -P <profile name>

Where "profile name" is any of the following:

    1. loadBalancer
    2. matrixServer
    3. matrixClient

In order for this project to function properly, the above profiles should be run in that order.
That is, a histogram server requires a load balancer to properly function, and an image client
requires a load balancer and a histogram server to function properly.

Hence, the load balancer should be run first. Then any matrix servers should be set up.
At this point, image clients will be able to successfully connect and retrieve data.

Configuration
-------------


Test Data
---------
Provided in the scripts folder is a python script titled 'generateData.py' which generates
a file of matrices in the proper format for this project. The syntax to run this script is
as follows:

    ./scripts/generateData.py

Further details are specified within the script comments.

Performance
-----------
This project was tested using data generated by the included script to demonstrate its performance
potential and scalability.

The results of our testing are shown in the graphs below.

Deployment
----------
A fast deploy script is included with this project in the scripts directory.

Authors
-------
- Christian Sherland
- Michael Scibor
- Ethan Lusterman
