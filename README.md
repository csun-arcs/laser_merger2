# laser_merger2
Muilti laser merger to pointcloud2 and laserScan for ROS2.

## Built with

- ROS Humble under Ubuntu 22.04 LTS

------

## Getting Started

### Installation

``` bash
$ git clone https://github.com/qaz9517532846/laser_merger2.git
```

### ROS2 topic

------

| Topic                              | Description                                                       |
| ---                                | ---                                                               |
| pointcloud                         | Merger pointcloud2 msg.                                           |
| scan                               | Merger laser scan msg.                                            ||

| Parameter                          | Description                                                       |
| ---                                | ---                                                               | 
| target_frame                       | target tf frame(Default: "base_link").                            |
| scan_topics                        | List of topics on which to read the laser scans                   |
| scan_reliability_policies          | List of QoS reliability policies per scan topic                   |
| scan_history_policies              | List of QoS history policies per scan topic                       |
| scan_depths                        | List of QoS depths per scan topic                                 |
| scan_durability_policies           | List of QoS durability policies per scan topic                    |
| point_cloud_topics                 | List of topics on which to read the point clouds (PointCloud2)    |
| point_cloud_reliability_policies   | List of QoS reliability policies per point cloud topic            |
| point_cloud_history_policies       | List of QoS history policies per point cloud topic                |
| point_cloud_depths                 | List of QoS depths per point cloud topic                          |
| point_cloud_durability_policies    | List of QoS durability policies per point cloud topic             |
| transform_tolerance                | TF transform tolerance.                                           |
| rate                               | Publish rate(Hz).                                                 |
| max_range                          | Merge laser scan max range.                                       |
| min_range                          | Merge laser scan min range.                                       |
| max_angle                          | Merge laser scan max angle.                                       |
| min_angle                          | Merge laser scan min angle.                                       |
| scan_time                          | Merge laser scan scan time.                                       |
| angle_increment                    | Merge laser scan angle increment.                                 |
| inf_epsilon                        | inf epsilon value.                                                |
| use_inf                            | use inf.                                                          |
| output_pointcloud_topic            | Name of the output merged point cloud topic                       |
| output_scan_topic                  | Name of the output merged scan topic                              ||

### Run

------

``` bash
$ ros2 launch laser_merger2 laser_merger.launch.py
```
For example:
``` bash
$ ros2 launch laser_merger2 laser_merger.launch.py target_frame:=base scan_topics:="[/lidar, /lidar2]" output_pointcloud_topic:=/merged_pcl
```

Note that laser_merger2 can merge `LaserScan` and/or `PointCloud2` messages, depending on the topics you provide with the `scan_topics` and `point_cloud_topics` arguments.

### Result

------

1. Laser 1 Data

![image](https://github.com/qaz9517532846/laser_merger2/blob/main/image/front_laser.png)

2. Laser 2 Data

![image](https://github.com/qaz9517532846/laser_merger2/blob/main/image/rear_laser.png)


3. Merge Process Data Result

![image](https://github.com/qaz9517532846/laser_merger2/blob/main/image/merger_laser.png)

------

## Reference:

[1]. pointcloud_to_laserscan, https://github.com/ros-perception/pointcloud_to_laserscan

------

## License:

This repository is for your reference only. copying, patent applications, and academic journals are strictly prohibited.

Copyright © 2023 ZM Robotics Software Laboratory.

## Acknowledgements

I would like to express our sincere thanks to [@leroycorentin](https://github.com/leroycorentin) for supporting ROS2 Humble contributions to this project.
