# Unused-args-moveit

roslaunch <moveit_config...> <execution_planning...launch>

Error: RLException: unused args [execution_type] for include of [moveit_controller_manager.launch.xml]

Caused by moveit generating buggy code sometimes.
Solution: Under launch files edit trajectory launch file and comment the last argument.

So that it becomes:

"<include file="$(find myur5_moveit_config)/launch/$(arg moveit_controller_manager)_moveit_controller_manager.launch.xml">"
"    <!--arg name="execution_type" value="$(arg execution_type)" /-->"
"</include>"

Note: I am unsure if this is a temporary solution or if this might be a little wrong but works for me!
