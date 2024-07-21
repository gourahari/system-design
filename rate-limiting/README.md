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

### Different Rate Limiting Algorithms
- **Fixed Window Rate Limiting**
  - Tracks the number of requests within a fixed time window. e.g.: One minute, one hour etc
  - Requests exceeding a predefined threshold within the window are rejected or delayed until the windows resets.
  - This algorithm profiles a straight forward technique to limit the rate of requests over a short period. But it may not handle traffic bursts effectively.
  - _**Example:** Allow upto 250 requests per minute._
- **Sliding Window Rate Limiting**
  - The sliding window log algorithm maintains a log of timestamps for each request received.
  - Requests older than a predefined time interval are removed from the log and new requests are accepted.
  - The rate of request is calculated based on the number of requests within the sliding window.
  - This algorithm allows for more precise rate limiting and better handling of traffic bursts compared to fixed window rate limiting.
  - _**Example:** Allow upto 100 requests in any 60 seconds window._
- **Token Bucket Rate Limiting**
  - It allocates tokens at a fixed rate into a bucket.
  - Each request consumes a token from the bucket and requests are allowed only if there are sufficient tokens available in the bucket.
  - Unused tokens are stored in the bucket upto a maximum capacity.
  - It provides a simple and flexible way to control the rate of requests and smooth out traffic bursts.
  - _**Example:** Allow upto 100 tokens per minute. Each request consumes one token._
- **Leaky Bucket Rate Limiting**
  - It models a bucket with a leakage where requests are added at a constant rate and leak out at a controlled rate.
  - Requests are allowed if the bucket has enough space, and excess requests are rejected.
  - This algorithm enforces a maximum request rate while allowing some traffic bursts.
  - _**Example:** Allow upto 200 requests with a leak rate of 15 requests per second._
- **API Based Rate Limiting**
  - Usually some apis are less frequently called compared to others.
  - Hence number of requests allowed for the frequent apis will be definitely more than that of the less frequent ones.
  - _**Example:** Usually login/signup apis are called less frequently than the others. Hence 10 req/sec for login api is fine compared to 60 req/sec for the other apis._
- **Role Based Rate Limiting**
  - This is similar to the API based Rate Limiting. Some admin apis are less frequently called compared to the user apis.
  - The production support apis are usually called only when there are production issues.
  - Hence number of requests allowed for the frequent apis will be definitely more than that of the less frequent ones.
- **Distributed Rate Limiting**
  - It involves rate limiting across multiple nodes of a system to handle traffic loads and improve scalability.
  - Techniques such as consistent hashing, token passing or distributed caches are used to control rate limiting across nodes.
  - _**Example:** Distributed rate limiting across multiple API gateways or load balancers._
- **Adaptive Rate Limiting**
  - It adjusts the rate limiting dynamically based on the system load, traffic patterns etc.
  - _**Example:** Automatically adjust rate limits based on server load or response times._
