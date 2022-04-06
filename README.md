# ROS2
xhost +
docker-compose up
. /ros2_foxy/install/local_setup.bash
ign service -s /world/empty/create --reqtype ignition.msgs.EntityFactory --reptype ignition.msgs.Boolean --timeout 1000 --req 'sdf_filename: "/models/robot_for_gazebo/rtvfin/urdf/rtvfin.urdf", name: "urdf_model"' data: true


export GAZEBO_MODEL_PATH=/models
export GAZEBO_RESOURCE_PATH=/models
export IGN_GAZEBO_RESOURCE_PATH=/models
ign gazebo empty.sdf