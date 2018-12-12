cmake_minimum_required (VERSION 2.8.8)
project (tf_inference)
 
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -g -std=c++11 -W")


link_directories(/usr/local/lib)



include_directories(
   include
   /usr/local/include
   /usr/local/include/bazel-genfiles
   /usr/local/include/opencv2
   /notebooks/tensorflow/bazel-bin/tensorflow
   /notebooks/tensorflow/tensorflow/contrib/makefile/downloads/nsync/public
   /usr/local/include/eigen3
   ) 
add_executable(tf_inference  tf_inference.cpp) 
target_link_libraries(tf_inference tensorflow_cc tensorflow_framework opencv_imgcodecs opencv_imgproc opencv_core opencv_highgui)

