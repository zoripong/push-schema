# push schema

push 서비스에 대한 proto3로 작성된 interface definition

## generate python stub

```bash
export SRC_DIR="$WORKSPACE/push-schema"
export DST_DIR="$WORKSPACE/simple-push-service/app/rpc"
python -m grpc_tools.protoc -I=$SRC_DIR --python_out=$DST_DIR --grpc_python_out=$DST_DIR $SRC_DIR/push.proto
```

## generate go stub

```
zoripong/workspace  > cd $WORKSPACE
zoripong/workspace  > protoc --go_out=plugins=grpc:./go/src/github.com/zoripong/simple-chat-service -I=./push-schema ./push-schema/push.proto
```

## related repository
- python push service: https://github.com/zoripong/simple-push-service
- go push client: https://github.com/zoripong/simple-chat-service
