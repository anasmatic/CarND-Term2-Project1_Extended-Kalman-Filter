# Extended Kalman Filter Project 
Udacity Self-Driving Car Engineer Nanodegree Program

In this project I will use kalman filter to estimate the state of a moving object with help of lidar and radar measurements.

## How to build
I was using Windows 10 and VisualStudio17

-to build this project using Bash for window :
* navigate to projet
* write cmd : mkdir build
* then navigate to build
* write cmd : cmake .. -G "Unix Makefiles" && make

## Project Docs

* first I have to initialize Vectors and Matrices 
    + Vectors and Matrices related to radar and laser inputs
    + Vectors and Matrices related to Kalman Filter Equations (x, P, R, H, F, ..etc)
* then handle the first measurement - Initialization step-
    + if data coming from laser we pass it to x vector as it is
    + if data coming from radar we convert it from polar to cartesian, then pass it to x vector
* then after initialization we handle predict and update steps
    + save the change in time, and modify F martix with new time
    + update covariance matrix Q using noise and delta time
    + then Predict
    + after that we use the Update function
        + if laser data : we do standerd kalman filter
        + if rader data : we have to use Jacobian matrix to convert H matrix to get Rho, Phi , & Rho dot
	+ update function will result x and P values, 
    + then evaluate these values with RMSE fucntion
