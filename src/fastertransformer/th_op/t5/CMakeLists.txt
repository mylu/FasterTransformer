# Copyright (c) 2019-2023, NVIDIA CORPORATION.  All rights reserved.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

add_library(th_t5 STATIC T5EncoderOp.cc T5DecodingOp.cc)
set_property(TARGET th_t5 PROPERTY POSITION_INDEPENDENT_CODE  ON)
target_link_libraries(th_t5 PRIVATE "${TORCH_LIBRARIES}" T5Encoder T5Decoder T5Decoding th_utils nccl_utils)
