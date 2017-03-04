FROM debian:8

RUN apt-get update

# git
RUN apt-get install -y git

# heimdall
RUN git clone --depth=1 https://github.com/Benjamin-Dobell/Heimdall.git

# dependencies
RUN apt-get install -y build-essential cmake zlib1g-dev qt5-default \
                       libusb-1.0-0-dev libgl1-mesa-glx libgl1-mesa-dev

# build
RUN mkdir Heimdall/build
RUN cd Heimdall/build && \
    cmake -DCMAKE_BUILD_TYPE=Release .. && \
    make

ENTRYPOINT ["/Heimdall/build/bin/heimdall"]
