# addsvc

addsvc is an example microservice which takes full advantage of most of Go
kit's features, including both service- and transport-level middlewares,
speaking multiple transports simultaneously, distributed tracing, and rich
error definitions. The server binary is available in cmd/addsvc. The client
binary is available in cmd/addcli.

Finally, the addtransport package provides both server and clients for each
supported transport. The client structs bake-in certain middlewares, in order to
demonstrate the _client library pattern_. But beware: client libraries are
generally a bad idea, because they easily lead to the
 [distributed monolith antipattern](https://www.microservices.com/talks/dont-build-a-distributed-monolith/).
If you don't _know_ you need to use one in your organization, it's probably best
avoided: prefer moving that logic to consumers, and relying on 
 [contract testing](https://docs.pact.io/best_practices/contract_tests_not_functional_tests.html)
to detect incompatibilities.

# 说明

* 这个示例中包含了
   * 限流
   * 熔断
   * 链路追踪zipkin  
   * 链路追踪opentrace ( 不考虑)
   * debug调试模式
   * http协议方式
   * grpc协议方式 
   * thrift协议方式
   * 目录结构划分

