# Start with a base image containing the necessary tools
FROM ubuntu:latest

# Install the necessary packages
RUN apt-get update && apt-get install -y \
  cmake \
  gcc-arm-none-eabi \
  libnewlib-arm-none-eabi \
  libstdc++-arm-none-eabi-newlib \
  git \
  python3 \
  g++ \
  && rm -rf /var/lib/apt/lists/*

# Clone the Raspberry Pi Pico SDK repository
RUN git clone https://github.com/raspberrypi/pico-sdk.git

RUN git clone https://github.com/raspberrypi/pico-extras.git
RUN git clone https://github.com/Wren6991/PicoDVI.git
RUN git clone https://github.com/fruit-bat/pico-vga-332.git
RUN git clone https://github.com/fruit-bat/pico-zxspectrum.git
RUN git clone https://github.com/pimoroni/pimoroni-pico.git
RUN git clone https://github.com/fruit-bat/pico-dvi-menu
RUN git clone https://github.com/fruit-bat/pico-emu-utils
RUN git clone https://github.com/redcode/Z80.git
RUN git clone https://github.com/redcode/Zeta.git

# Install the Raspberry Pi Pico SDK repository
RUN cd pico-sdk && git submodule update --init
# Set the PICO_SDK_PATH environment variable
ENV PICO_SDK_PATH=/pico-sdk

# # Install the Raspberry Pi Pico SDK repository
RUN cd ../pico-extras && git submodule update --init
# # Set the PICO_SDK_PATH environment variable
ENV PICO_EXTRAS_PATH=/pico-extras

# #back to the root dir
# RUN CD ..

# Create a new directory for the build
RUN mkdir build

# Set the workdir to the build directory
WORKDIR /build