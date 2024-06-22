# SIMD (Smartphone Inertial Measurement Dataset)

Introduced by Liu et al. in [Smartphone-based Pedestrian Inertial Tracking:
Dataset, Model, and Deployment](https://ieeexplore.ieee.org/document/10373097)。

Please note that if you want to use the SIMD dataset, please cite the paper:

> @article{liu2023smartphone,
  title={Smartphone-based Pedestrian Inertial Tracking: Dataset, Model, and Deployment},
  author={Liu, Feng and Ge, Hongyu and Tao, Dan and Gao, Ruipeng and Zhang, Zhang},
  journal={IEEE Transactions on Instrumentation and Measurement},
  year={2023},
  publisher={IEEE}
}

# SIMD Dataset

[The Smartphone Inertial Measurement Dataset](https://ieeexplore.ieee.org/document/10373097) is a crowdsourced set of inertial data for pedestrian tracking which is recorded by smartphones at 50 Hz in both indoor and outdoor environments. The suite consists of multiple indoor and outdoor scenarios, multiple poses of smartphones, and multiple users with different attributes. The above setup helps it to support the evaluation of algorithm performance in different conditions, which is beneficial for promoting research on data-driven inertial navigation based approaches.

Due to the different concerns, some information (for example, some of the environment settings) is not accurately described. In addition, the orientation of the ground trajectories contains only left and right right-angle turns, the orientation of the start position is determined by the user, and some of the trajectories contain data calibration actions at the beginning of the trajectory. This dataset is available at this repository.

The data in this repository are collected in **Beijing**, China. In particular, the outdoor data are collected in areas such as school playgrounds, and the indoor data are collected in underground parking garages in a school and a shopping mall.

# How to use SIMD Dataset

The dataset can be download from this repository. The relevant description of the dataset is as follows:

## Data Set Structure

The data set catalogue structure is divided according to scene, pose, and user.

- Indoor
    - Bag
        - user1
        - user2
        - user3
        - ...
    - Calling
        - user1
        - user2
        - user3
        - ...
    - Flat
        - user1
        - user2
        - user3
        - ...
    - Pocket
        - user1
        - user2
        - user3
        - ...
    - ...
- Outdoor
    - Bag
        - user1
        - user2
        - user3
        - ...
    - Calling
        - user1
        - user2
        - user3
        - ...
    - Flat
        - user1
        - user2
        - user3
        - ...
    - Pocket
        - user1
        - user2
        - user3
        - ...
    - ...

In each user sub-folder, multiple pieces of trajectory data collected by that user are included.


## Explanations of data fields

Table 1 shows the meaning and example of each field in the data file. Specifically, we capture sensor data such as accelerometers, gyroscopes, gravimeters, and rotation vectors, as well as GPS signals with smartphones.

<table>  
    <tr>    
        <td colspan="1" style="text-align:center;font-weight:bold;">Field Name</td>
        <td colspan="1" style="text-align:center;font-weight:bold;">Meaning</td>
        <td colspan="1" style="text-align:center;font-weight:bold;">Format</td>
        <td colspan="1" style="text-align:center;font-weight:bold;">Example</td>
        <td colspan="1" style="text-align:center;font-weight:bold;">Unit / Explanation</td>
    </tr>  
    <tr>    
        <td style="text-align:center;">Sys_time</td>   
        <td style="text-align:center;">System Timestamp</td>   
        <td rowspan="16" style="text-align:center;">String</td>  
        <td style="text-align:center;">1657537510025</td>  
        <td style="text-align:center;">Millisecond</td>  
    </tr> 
    <tr>   
        <td style="text-align:center;">laccx、y、z</td>    
        <td style="text-align:center;">Three-axis Linear Acceleration</td>    
        <td style="text-align:center;">-0.18167877,0.08573502,-1.3974676</td>  
        <td style="text-align:center;">m/s<sup>2</sup></td>  
    </tr>  
    <tr>   
        <td style="text-align:center;">grax、y、z</td>   
        <td style="text-align:center;">Three-axis Gravity</td>   
        <td style="text-align:center;">-0.400577,0.59512204,9.7803755</td> 
        <td style="text-align:center;">m/s<sup>2</sup></td> 
    </tr> 
    <tr>    
        <td style="text-align:center;">gyrx、y、z</td>    
        <td style="text-align:center;">Three-axis Gyroscope</td>    
        <td style="text-align:center;">-0.0013315412,-0.10492545,-0.4908061</td>  
        <td style="text-align:center;">radians/second</td>  
    </tr> 
    <tr>    
        <td style="text-align:center;">accx、y、z</td>    
        <td style="text-align:center;">Three-axis Acceleration</td>    
        <td style="text-align:center;">-0.9927223,0.87607217,9.02812</td>  
        <td style="text-align:center;">m/s<sup>2</sup></td>  
    </tr> 
    <tr>    
        <td style="text-align:center;">magx、y、z</td>    
        <td style="text-align:center;">Three-axis Magnetic Field</td>    
        <td style="text-align:center;">6.7344,29.036,-48.007</td>  
        <td style="text-align:center;">micro-Tesla (uT)</td>  
    </tr> 
    <tr>    
        <td style="text-align:center;">rot_x</td>    
        <td style="text-align:center;">The x-axis component of the rotation vector</td>    
        <td style="text-align:center;">0.0360762</td>  
        <td rowspan="3"  style="text-align:center;">The three elements of the rotation vector are < x*sin(θ/2), y*sin(θ/2), z*sin(θ/2) >, such that the magnitude of the rotation vector is equal to sin(θ/2), and the direction of the rotation vector is equal to the direction of the axis of rotation.</td>  
    </tr> 
    <tr>    
        <td style="text-align:center;">rot_y</td>    
        <td style="text-align:center;">The y-axis component of the rotation vector</td>    
        <td style="text-align:center;">-0.008802953</td>   
    </tr> 
    <tr>    
        <td style="text-align:center;">rot_z</td>    
        <td style="text-align:center;">The z-axis component of the rotation vector</td>    
        <td style="text-align:center;">-0.7470763</td>  
    </tr> 
    <tr>    
        <td style="text-align:center;">grot_x</td>    
        <td style="text-align:center;">The x-axis component of the game rotation vector</td>    
        <td style="text-align:center;">0.027475474</td>  
        <td rowspan="3" style="text-align:center;">In the ideal case, a phone rotated and returning to the same real-world orientation will report the same game rotation vector (without using the earth's geomagnetic field).</td>  
    </tr> 
    <tr>    
        <td style="text-align:center;">grot_y</td>    
        <td style="text-align:center;">The y-axis component of the game rotation vector</td>    
        <td style="text-align:center;">0.024180705</td>
    </tr> 
    <tr>    
        <td style="text-align:center;">grot_z</td>    
        <td style="text-align:center;">The z-axis component of the game rotation vector</td>    
        <td style="text-align:center;">0.12881209</td>
    </tr> 
    <tr>    
        <td style="text-align:center;">lon</td>    
        <td style="text-align:center;">GPS Longitude</td>    
        <td style="text-align:center;">116.33895892</td>  
        <td style="text-align:center;">degree</td>  
    </tr> 
    <tr>    
        <td style="text-align:center;">lat</td>    
        <td style="text-align:center;">GPS Latitude</td>    
        <td style="text-align:center;">39.95110953</td>  
        <td style="text-align:center;">degree</td>  
    </tr> 
    <tr>    
        <td style="text-align:center;">speed</td>    
        <td style="text-align:center;">GPS Speed</td>    
        <td style="text-align:center;">0.46</td>  
        <td style="text-align:center;">m/s</td>  
    </tr> 
    <tr>    
        <td style="text-align:center;">bearing</td>    
        <td style="text-align:center;">GPS Bearing</td>    
        <td style="text-align:center;">355.4</td>  
        <td style="text-align:center;">degree</td>  
    </tr> 
</table>

