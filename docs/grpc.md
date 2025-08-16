---
hide:
  - navigation
---

# gRPC

## gRPC with Python
poetry init
poetry add grpcio grpcio-tools

Generate grpc code from proto:


Important note: When generating grpc code to a subfolder, the abolute path imports would break and has to be either manually fixed or use [workaround of placing proto file in certain subfolder](https://stackoverflow.com/questions/62818183/protobuf-grpc-relative-import-path-discrepancy-in-python).

## Courses
- [Complete gRPC Course](https://www.youtube.com/playlist?list=PLy_6D98if3UJd5hxWNfAqKMr15HZqFnqf)
- [Introduction to Protocol Buffers](https://training.linuxfoundation.org/training/introduction-to-protocol-buffers-lfs145/) by Linux Foundation

## Tools
1. [grpcurl](https://github.com/fullstorydev/grpcurl)
2. [grpcui](https://github.com/fullstorydev/grpcui)
3. [grpc-gateway](https://github.com/grpc-ecosystem/grpc-gateway)
4. [grpc-dump](https://github.com/bradleyjkemp/grpc-tools?tab=readme-ov-file#grpc-dump)

## Curated Lists
1. [Awesome gRPC](https://github.com/grpc-ecosystem/awesome-grpc) - Curated list of useful tools and resources for use in gRPC ecosystem