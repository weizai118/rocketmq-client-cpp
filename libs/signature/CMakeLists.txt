# Licensed to the Apache Software Foundation (ASF) under one or more
# contributor license agreements.  See the NOTICE file distributed with
# this work for additional information regarding copyright ownership.
# The ASF licenses this file to You under the Apache License, Version 2.0
# (the "License"); you may not use this file except in compliance with
# the License.  You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

project(signature)

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include)
set(LIBRARY_OUTPUT_PATH ${CMAKE_CURRENT_SOURCE_DIR}/lib)

aux_source_directory(src/  DIR_LIB_SRCS)

add_library(Signature STATIC ${DIR_LIB_SRCS})
target_link_libraries(Signature ${deplibs})
set_target_properties(Signature PROPERTIES OUTPUT_NAME "Signature")

# install
install (TARGETS   Signature             DESTINATION lib)
#install (DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/include/ DESTINATION include/rocketmq)
