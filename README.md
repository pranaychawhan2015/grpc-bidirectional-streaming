This is basic example of gRPC based microservice to serve a Virtual Stack Machine over HTTP2.0 network.

# Pre-requisites
```bash
# install protobuf compiler
~/grpc-bidirectional-streaming
$ go get -u -v github.com/golang/protobuf/{proto,protoc-gen-go}

#set GOPATH in .bashrc
export PATH="$PATH:$(go env GOPATH)/bin"
source ~/.bashrc

# install grpc
~/grpc-bidirectional-streaming
$ go get -u -v google.golang.org/grpc
```
# Generate Go Source Code from Protobuf
```bash
~/grpc-bidirectional-streaming
$ SRC_DIR=./machine
$ DST_DIR=$SRC_DIR
$ protoc -I=$SRC_DIR --go-grpc_out=$DST_DIR $SRC_DIR/machine/machine.proto
```

# Run
```bash
~/grpc-bidirectional-streaming
$ go run cmd/run_machine_server.go
$ go run client/machine.go
```

