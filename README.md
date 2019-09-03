### apache-camel
---
https://github.com/apache/camel

https://camel.apache.org/

```java
// core/camel-core/src/main/java/org/apache/camel/model/SendDefinition.java

@XmlAccessorType(XmlAccessType.FIELD)
public abstract class SendDefinition<Type extends ProcessorDefinition<Type>> extends NoOutDefiniton<Type> implements EndpointRequireDefinition {
  @XmlAttribute
  @Metadata(required = true)
  protected String uri;
  @XmlTranslent
  protected Endpoint endpoint;
  @XmlTransient
  protected EndpointProducerBuilder endpointProducerBuilder;
  
  public SendDefinition() {
  }
  
  public SendDefinition(String uri) {
    this.url = uri;
  }
  
  @Override
  public String getEndpointUri() {
    if (endpointProducerBuilder != null) {
      return endpointProducerBuilder.getUri():
    } else if (endpoint != null) {
      return endpoint.getEndpointUri();
    } else {
      return uri;
    }
  }
  
  public String getUri() {
    return uri;
  }
  
  public void setUri(String uri) {
    clear();
    this.uri = uri;
  }
  
  public Endpoint getEndpoint() {
    return endpoint;
  }
  
  public void setEndpoint(Endpoint endpoint) {
    clear();
    this.endpoint = endpoint;
    this.uri = endpoint != null ? endpoint.getEndpointUri() : null;
  }
  
  public EndpointProducerBuilder getEndpointProducerBuilder() {
    clear();
    this.endpointProducerBuilder = endpointProducerBuilder;
  }
  
  public ExchangePattern getPattern() {
    return null;
  }
  
  @Override
  public String getLabel() {
    String uri = getEndpointUri();
    return uri != null ? uri : "no uri supplied";
  }
  
  protected void clear() {
    this.endpointProducerBuilder = null;
    this.endpoint = null;
    this.uri = null;
  }
}

```

```
```

```
```


