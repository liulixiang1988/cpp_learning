FROM gcc:13.2.0

ARG BOOST_VERSION=1.83.0

RUN apt-get -qq update && apt-get -qq upgrade 

RUN apt-get install -y \
    cmake \
    build-essential

# Install Boost
# https://www.boost.org/doc/libs/1_80_0/more/getting_started/unix-variants.html
RUN cd /tmp && \
    BOOST_VERSION_MOD=$(echo $BOOST_VERSION | tr . _) && \
    wget https://boostorg.jfrog.io/artifactory/main/release/${BOOST_VERSION}/source/boost_${BOOST_VERSION_MOD}.tar.bz2 && \
    tar --bzip2 -xf boost_${BOOST_VERSION_MOD}.tar.bz2 && \
    cd boost_${BOOST_VERSION_MOD} && \
    ./bootstrap.sh --prefix=/usr/local && \
    ./b2 install && \
    rm -rf /tmp/*


RUN apt-get install -y \
    #libboost-all-dev=1.74.0.3 \
    libtcmalloc-minimal4 \
    libgoogle-perftools-dev \
    && ln -s /usr/lib/libtcmalloc_minimal.so.4 /usr/lib/libtcmalloc_minimal.so
