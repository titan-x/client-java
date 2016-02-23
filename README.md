# Titan Java Client

[![Build Status](https://travis-ci.org/titan-x/client-java.svg?branch=master)](https://travis-ci.org/titan-x/client-java)

Titan client implementation for Java. Also works on Android. Depends on [Neptulon Java client](https://github.com/neptulon/client-java). Requirements and dependencies for Neptulon Java client is listed on its own repo.

## Example

```java
Conn conn = new ConnImpl("ws://127.0.0.1:3001");
conn.middleware(new Logger());
conn.connect();
conn.sendRequest("hello", new EchoMessage("Hello from Java client!"), new ResHandler<Object>() {
  @Override
  public Class<Object> getType() {
    return Object.class;
  }

  @Override
  public void handler(Response<Object> res) {
    System.out.println("Received hello message response: " + res.result);
  }
});
```

## Building

```bash
./gradlew build
```

## Testing

Start a Titan server at local address: `127.0.0.1:3001` and then:

```bash
./gradlew check
```

## License

[MIT](LICENSE)
