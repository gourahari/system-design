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
