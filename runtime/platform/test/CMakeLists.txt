# Copyright (c) Meta Platforms, Inc. and affiliates.
# All rights reserved.
#
# This source code is licensed under the BSD-style license found in the
# LICENSE file in the root directory of this source tree.

# This file should be formatted with
# ~~~
# cmake-format -i CMakeLists.txt
# ~~~
# It should also be cmake-lint clean.
#

cmake_minimum_required(VERSION 3.19)

set(EXECUTORCH_ROOT ${CMAKE_CURRENT_SOURCE_DIR}/../../..)

include(${EXECUTORCH_ROOT}/tools/cmake/Test.cmake)

et_cxx_test(platform_test SOURCES executor_pal_test.cpp)

et_cxx_test(platform_runtime_override_test SOURCES executor_pal_runtime_override_test.cpp stub_platform.cpp)

et_cxx_test(platform_static_runtime_override_test SOURCES executor_pal_static_runtime_override_test.cpp)

# TODO: Re-enable this test on OSS
# et_cxx_test(platform_death_test SOURCES executor_pal_death_test.cpp)

et_cxx_test(logging_test SOURCES logging_test.cpp)

# TODO: Re-enable this test on OSS
# et_cxx_test(clock_test SOURCES clock_test.cpp stub_platform.cpp)
