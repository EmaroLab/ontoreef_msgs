cmake_minimum_required(VERSION 2.8.3)
project(ontoreef_msgs)

find_package(catkin REQUIRED COMPONENTS
   message_generation #    genmsg
   pitt_msgs
   std_msgs
   sensor_msgs
   pcl_msgs
)

# add_message_files(
#    DIRECTORY msg 
#    FILES
# )

add_service_files(DIRECTORY srv
  FILES
  ParserExchange.srv
  PerceptionExchange.srv
  PlannerExchange.srv)

generate_messages(
   DEPENDENCIES
   pitt_msgs
   std_msgs
   sensor_msgs
   pcl_msgs
)

catkin_package(CATKIN_DEPENDS message_runtime)
