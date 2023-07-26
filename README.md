# beu-ros-interfaces
This ROS package include all the ROS message type we use in the beu environment.

## Messages Type
![](https://img.shields.io/badge/BoundingBox.msg-grey?style=for-the-badge)

Built from coordinates of the top right corner and the bottom left corner of the bounded object, and the matching frame_id of the tracked frame.

* int64 xmin
* int64 ymin
* int64 xmax
* int64 ymax
* int16 frame_id
<br> <br />

![](https://img.shields.io/badge/TrackerResult.msg-grey?style=for-the-badge)

Built from the BoundingBox message listed above :point_up_2:,
a boolian flag that indicates whether the algorithem is tacking or not, and a score which indicates the quality of the tracking.

* BoundingBox bounding_box
* std_msgs/Bool flag
* std_msgs/Float32 score

<br> <br />
## Services Message Type
![](https://img.shields.io/badge/InitTracker.srv-grey?style=for-the-badge)

The ROS service messages are built from a service_request and a service_response, both defined and generated from the init_service.srv file, which in our case is InitTracker.srv

### InitTrackerRequest
Built from a frame (image object) - the frame that the user clicked his requested bounding box on, and the bounding box themselves.

* sensor_msgs/Image frame
* BoundingBox bounding_box

---
### InitTrackerResponse
Built from a boolian varlabile which indicates whether the service callback managed to initialized the tracker properly or not.

* std_msgs/Bool ack