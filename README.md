# Titan Java Client

[![Build Status](https://travis-ci.org/titan-x/client-java.svg?branch=master)](https://travis-ci.org/titan-x/client-java)

Titan client implementation for Java. Also works on Android. Depends on [Neptulon Java client](https://github.com/neptulon/client-java). Requirements and dependencies for Neptulon Java client is listed on its own repo.

## Example

```java
Client client = new ClientImp("ws://127.0.0.1:3000");
client.connect(new ConnCallback() { ... });
client.jwtAuth(JWT_TOKEN, new JwtAuthCallback() {
    @Override
    public void success() {
        System.out.println("JWT auth done");
    }

    @Override
    public void fail() {
        System.out.println("JWT auth failed");
    }
});

// now you can use `client.sendMessages(...)`
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
