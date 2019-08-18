### tracer
---
https://github.com/zalando/tracer

```java
Tracer delegate = ...;
APIExtensionsTracer tracer = new APIExtensionsTracer(delegate);
tracer.addTracerObserver(new MDCSpanObserver());

context.addFilter("FlowFilter", new FlowFilter(flow))
  .addMappingForUrlPatterns(EnumSet.of(REQUEST), true, "/*");

DefaultHttpClient client = new DefaultHttpClient();
client.addRequestInterceptor(new FlowHttpRequestInterceptor(flow));

OkHttpClient client = new OkHttpClient.Builder()
  .addNetworkInterceptor9new FlowInterceptor(flow))
  .build();
  
Flow flow = Flow.create(tracer);

entity.setLastModifiedBy(flow.currentId());

```

```
tracer:
  filter.enabled: true
  mdc.enabled: true
```

```
```


