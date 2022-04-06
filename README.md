# ROS2
Даем доступ к X-серверу
```
xhost +
```
Запускаем доккер контейнер
```
docker-compose up
```
Заходим в доккер контейнер foxy_ign и выполняем

```
. /ros2_foxy/install/local_setup.bash #инициализация ROS2
ign gazebo empty.sdf #запуск ignition gazebo с пустым миром
```
В графическом интерфейсе должен появиться ignition gazebo

Открываем еще один терминал доккер контейнера foxy_ign

Данная команда импортирует URDF файл модели робота в ignition gazebo 
```
ign service -s /world/empty/create --reqtype ignition.msgs.EntityFactory --reptype ignition.msgs.Boolean --timeout 1000 --req 'sdf_filename: "/models/robot_for_gazebo/rtvfin/urdf/rtvfin.urdf", name: "urdf_model"' data: true
```