# Navigation

The navigation module uses the ROS navigation stack with Adaptive Monte-Carlo Localization (ACML) for localization, the Dijkstra algorithm as global planner over the global costmap and the Dynamic Window Approach (DWA) as local planner over the local costmap. We use a corrected version of the naoqi driver ROS package to access lidars and depth camera data. The information provided from Pepper’s lidar is insufficient for computing costmaps, therefore depth camera PointClouds are added as inputs, allowing Pepper to detect objects that could be out of range from its lidars sensing capability, such as detecting tables or chairs. 

In addition, RoboBreizh uses Spatio-Temporal Voxel Layer as a 2D local costmap plugin continuously adding a new layer of weight of temporary obstacles at every runtime of detecting moving obstacles in a dy- namic environment. With the contribution from the voxel layer and DWA, our
Pepper robot is able to safely navigate in a known environment as well as avoiding dynamic obstacles. 

Timed Elastic Bands local planner TEB was also tested as local planner to dynamically avoid obstacles, however, such methodology is resource intensive. For Simultaneous Localization And Mapping (SLAM) we planned to use Octomap, but nevertheless, a lot of drifts were happening
in the competition which made mapping unreliable using this technique. Thus, we use manual created map.