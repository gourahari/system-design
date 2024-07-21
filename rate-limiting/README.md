# Rate Limiting

- Rate limiting in system design is a very important concept. It controls the incoming traffic to a system.
- It plays an important role in performance improvement, restricting api bombardment, preventing overload and enhancing security.

![image](https://github.com/user-attachments/assets/62c6f07f-af54-4b48-908a-5cddc89c4e8e)

### Roles of Rate limiting in System design
- **Preventing Overload:** It helps prevent overload situations by controlling the rate of incoming requestsor actions.
- **Ensuring Stability:** By regulating the traffic flow, it helps ensure system stabiity and prevents resource exhaustion.
- **Mitigating DoS Attacks:** it is an effective defense mechanism against Denial-Of-Service attacks where the attacker tries to bombard the system with loads of requests to disrupt its operation.
- **Fair Resource Allocation:** Rate limiting supports fair resource allocation ensuring all users have equitable access to the resources. By limiting the rate of requests, system can prevent certain users from monopolizing resources.
- **Optimizing Performance:** It can help optimize system performance by preventing excessive resource consumption and improving response times.
- **Protecting Against Abuse:** It helps protect systems against abuse or misuse by limiting the frequency of requests from individual requests.

### Types of Rate Limiting
- **Fixed Window Rate Limiting:** In this, a fixed time window is used to track the number of requests allowed within that window.
  - _**Example:** Allow upto 250 requests per minute._
- **Sliding Window Rate Limiting:** It dynamically tracks the rate of requests within a time window, which continuously moves forward with time. Requests are counted within the window, and if the limit is exceeded, subsequent requests are rejected or delayed until the windows moves forward.
  - _**Example:** Allow upto 100 requests in any 60 seconds window._
- **Token Bucket Rate Limiting:** It allocates tokens at a fixed rate over time into a bucket. Each requests consumes one token from the bucket. Requests are allowed only if there are sufficient tokens in the bucket. Otherwise, requests are delayed or rejected ubtil tokens become available.
  - _**Example:** Allow upto 100 tokens per minute. Each request consumes one token._
- **Leaky Bucket Rate Limiting:** It models a bucket with a leakage where requests are added at a constant rate and leak out at a controlled rate. Requests are allowed if the bucket has enough space, and excess requests are rejected.
  - _**Example:** Allow upto 200 requests with a leak rate of 15 requests per second._
- **Distributed Rate Limiting:** It involves rate limiting across multiple nodes of a system to handle traffic loads and improve scalability. Techniques such as consistent hashing, token passing or distributed caches are used to control rate limiting across nodes.
  - _**Example:** Distributed rate limiting across multiple API gateways or load balancers._
- **Adaptive Rate Limiting:** It adjusts the rate limiting dynamically based on the system load, traffic patterns etc.
  - _**Example:** Automatically adjust rate limits based on server load or response times._
