# Bundling prebuilt librdkafka

Prebuilt statically linked librdkafka v1.3.0 for linux.

Built with,

```
docker run -it --entrypoint /bin/bash ubuntu:bionic
apt-get update
apt-get install -y git gcc g++ python make cmake
cd /home
git clone https://github.com/edenhill/librdkafka.git
cd librdkafka
git checkout v1.3.0 -b v1.3.0
cmake -H. -B_cmake_build -DRDKAFKA_BUILD_STATIC=ON -DWITH_ZSTD=OFF -DWITH_ZSTD=OFF -DWITH_SSL=OFF -DWITH_SASL=OFF -DENABLE_LZ4_EXT=OFF -DWITH_LIBDL=OFF
cmake --build _cmake_build
cmake --build _cmake_build --target install
```

```
docker cp musing_pasteur:/usr/local/lib/librdkafka.a .
docker cp musing_pasteur:/usr/local/include/librdkafka/rdkafka.h .
```
