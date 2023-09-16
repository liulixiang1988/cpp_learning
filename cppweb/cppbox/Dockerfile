FROM gcc:13.2.0

RUN apt-get update && apt-get install -y \
    cmake \
    libboost-all-dev \
    build-essential \
    libtcmalloc-minimal4 \
    libgoogle-perftools-dev \
    && ln -s /usr/lib/libtcmalloc_minimal.so.4 /usr/lib/libtcmalloc_minimal.so