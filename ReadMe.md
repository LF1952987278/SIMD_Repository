# Description of the SIMD data set

This repository is used to maintain the SIMD data set presented in the paper entitled "xxx".

The data set captures IMU and GPS data from smartphones, which contains multiple scenarios, poses, and users.

Scenes include school playgrounds, underground parking garages in schools and shopping malls, etc. Poses include placing the the smartphone flat, holding the phone for calling, placing the phone in the bags or pockets, swinging the arm, etc. The outdoor data take the GPS information as the ground truth, and the indoor data take the fixed route and manually recorded position as the trajectory ground truth.

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
* Outdoor
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

# Additional Information

可以参考Readme的word补充数据的详细信息。

- The outdoor walking trajectory is determined by the users, but the walking journey includes only straight ahead, left right-angle turn and right right-angle turn, and the initial 5s of each trajectory is straight ahead, while the direction facing at the starting position is also determined by the users. In addition, the large jitter at the beginning of the data for a period of time are caused by the user performing the dynamic calibration, which involves doing the eight-like actions in the air (for magnetometer calibration) and keeping the smartphone in the flat attitude for five seconds (for accelerometer calibration).

- The indoor walking trajectory mainly completes the collection in the parking garage of the school and the shopping mall, the floor plan is shown below.

![Alt text](<scool parking lot.jpg>)
![Alt text](shoopingmallparkinglot_gray.jpg)

<img src="file://E:/documents/QQ/scool parking lot.jpg"  width="200" height="200" />





