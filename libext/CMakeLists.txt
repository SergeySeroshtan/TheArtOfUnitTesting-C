#   BSD 3-Clause License
#
#   Copyright (c) 2018, Sergey Seroshtan
#   All rights reserved.
#
#   Redistribution and use in source and binary forms, with or without
#   modification, are permitted provided that the following conditions are met:
#
#   * Redistributions of source code must retain the above copyright notice, this
#     list of conditions and the following disclaimer.
#
#   * Redistributions in binary form must reproduce the above copyright notice,
#     this list of conditions and the following disclaimer in the documentation
#     and/or other materials provided with the distribution.
#
#   * Neither the name of the copyright holder nor the names of its
#     contributors may be used to endorse or promote products derived from
#     this software without specific prior written permission.
#
#   THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
#   AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
#   IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
#   DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE
#   FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL
#   DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR
#   SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER
#   CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY,
#   OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
#   OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

cmake_minimum_required(VERSION 3.10 FATAL_ERROR)

# ---------------------------------------------------------------------------
#   Unity
# ---------------------------------------------------------------------------
add_library(unity "")
target_sources(unity
        PUBLIC
        "${CMAKE_CURRENT_LIST_DIR}/Unity/src/unity.h"
        "${CMAKE_CURRENT_LIST_DIR}/Unity/src/unity_internals.h"
        "${CMAKE_CURRENT_LIST_DIR}/Unity/src/unity.c")

target_include_directories(unity
        PUBLIC
        $<BUILD_INTERFACE:${CMAKE_CURRENT_LIST_DIR}/Unity/src>)

# ---------------------------------------------------------------------------
#   CMock
# ---------------------------------------------------------------------------
add_library(cmock "")
target_sources(cmock
        PUBLIC
        "${CMAKE_CURRENT_LIST_DIR}/CMock/src/cmock.h"
        "${CMAKE_CURRENT_LIST_DIR}/CMock/src/cmock_internals.h"
        "${CMAKE_CURRENT_LIST_DIR}/CMock/src/cmock.c")

target_include_directories(cmock
        PUBLIC
        $<BUILD_INTERFACE:${CMAKE_CURRENT_LIST_DIR}/CMock/src>
        PRIVATE
        $<BUILD_INTERFACE:${CMAKE_CURRENT_LIST_DIR}/Unity/src>)
