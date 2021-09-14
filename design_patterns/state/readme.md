

##### State Design Pattern - Behavioral

Use when; 

- An object's behavior depends on its state so it must its behavior when its state changed



Context class 

```java
public class TCPConntection {
    private TCPState tcpState;
    
    public void open() {
        tcpState.open();
    }
    
    public void close() {
        tcpState.close();
    }
    
    public void acknowledge() {
        tcpState.acknowledge();
    }
}
```



```java
public interface TCPState {
    
    void open();
    
    void close();
    
    void acknowledge();
}
```

```java
public class TCPListening implements TCPState {
    
    @Override
    public void open() {
        System.out.println("opening..");
    }
    
    @Override
    public void close() {
        System.out.println("closing..");
    }
    
    @Override
    public void acknowledge() {
        System.out.println("can not ack because not established..")
    }
} 
```

