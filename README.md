# object_pose_msgs

This package provides ROS message files representing pose information of objects. These message types can be used in simulation or in real applications to allow for the transfer, storage, and manipulation of information on 6D poses and bounding box data.

</br>

## Message Overview

</br>

**ObjectPose.msg**
 
The ObjectPose message is a base message type in this object_pose_msgs. The message contains information regarding the class (e.g. 'bottle') and instance of the object (e.g. 1). In addition, the message contains information representing the 6D pose of the object along with bounding box size and minimum/maximum bounding box points.  

    string class_id  //class of object, e.g. 'bottle'
    uint8 instance_id //instance of object, e.g. 1
    geometry_msgs/Pose pose //pose of object
    geometry_msgs/Vector3 size //size of object
    geometry_msgs/Vector3 min //minimum point of object bounding box
    geometry_msgs/Vector3 max //maximum point of object bounding box


</br>

**ObjectList.msg**
 
The ObjectList message contains an array of ObjectPoses, along with a single header. Since the ObjectPoses themeselves do not have any header information, the header in the ObjectList can be used to obtain header information for each contained object. (An example use case is that a camera observes several objects, all being observed at the same time and in the same frame_id. The time and frame_id information would be stored in the header of ObjectList, and each observed object would be added to the ObjectPose array)

    std_msgs/Header header //header information
    ObjectPose[] objects //array of ObjectPoses

</br>