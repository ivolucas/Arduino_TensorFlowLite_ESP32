# TensorFlowLite_ESP32

https://www.tensorflow.org/lite/microcontrollers/overview

## Overview

This library runs TensorFlow machine learning models on microcontrollers, allowing you to build AI/ML applications powered by deep learning and neural networks.

## How to make this library
```

git clone --branch v2.6.2 --depth 1 https://github.com/tensorflow/tensorflow.git
cd tensorflow
make -f tensorflow/lite/micro/tools/make/Makefile TARGET=esp generate_hello_world_esp_project # use gmake for OSX

# Take tensorflow/lite/micro/tools/make/gen/esp_xtensa-esp32/prj/hello_world/esp-idf/components/tfmicro/
# and replace the existing in the src dir

# Fix include paths
find src -type f -exec sed -i 's|#include "flatbuffers/|#include "third_party/flatbuffers/include/flatbuffers/|g' {} +
find src -type f -exec sed -i 's|#include "fixedpoint/|#include "third_party/gemmlowp/fixedpoint/|g' {} +
find src -type f -exec sed -i 's|#include "ruy/|#include "third_party/ruy/ruy/|g' {} +
```

