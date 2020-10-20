# Bundling prebuilt librdkafka

Prebuilt statically linked librdkafka v1.3.0 for linux.

Built with,

```
docker run -it --entrypoint /bin/bash buildkite/agent:3.24.0-ubuntu
apt-get update
apt-get install -y gcc g++ python make
git clone https://github.com/edenhill/librdkafka.git
cd librdkafka
git checkout v1.3.0 -b v1.3.0
./configure
make
make install
```
