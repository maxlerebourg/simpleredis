# simpleredis
Minimal go redis with only get, set and delete operation.
With NO extern dependencies.

```go
import simpleredis "github.com/maxlerebourg/simpleredis"

var redis simpleredis.SimpleRedis

redis.Init("redis:6379")

err := redis.Set("test", []bytes("whatever"), 60),  // Set key "test" with "whatever" for 60 seconds
if err != nil {
  ...
}
val, err := redis.Get("test") // get key test
if err != nil {
  // err could be only redis:unreachable, redis:miss or redis:timeout available in simpleredis.RedisUnreachable
  ...
}
err = redis.Del("test")
if err != nil {
  ...
}
```
