cmake_minimum_required(VERSION 3.8)
project(examen_bringup)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)

install(
DIRECTORY launch rviz worlds src
DESTINATION share/${PROJECT_NAME}/
)

# Install Python modules
ament_python_install_package(${PROJECT_NAME})

# Install Python executables #They must start with the shebag tag
install(PROGRAMS
  ${PROJECT_NAME}/tray_test.py
  ${PROJECT_NAME}/multi_tray.py
  #src/tray_test.py
  DESTINATION lib/${PROJECT_NAME} 
)

ament_package()
