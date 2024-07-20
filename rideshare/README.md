# Ride Share App (Ola/Uber/Lyft)

### Functional Requirements
- User should be able to view the available cabs with a price and ETA.
- User should be able to change the car type (Regular/Large/XL) according to his need.
- User should be able to book a cab.
- User should be able to view the driver and car details.
- User should be able to track live location of the driver.
- User should be able to cancel the ride whenever he want.

### Non-Functional Requirements
- Availability: The system should be highly available and reliable.
- Scalability: The system should be able to handle an increasing number of users (rider/driver)
- Consistency: The system should ensure a consistent view to the users.
- Security & Privacy: The system should ensure the security and privacy of users.
- Fault Tolerance: The system should be resilient to any kind of failures, with redundancy and failover mechanisms in place.+

### Capacity Planning
**Assumptions:**
- Active users: 5 million
- Active drivers: 250,000
- Average rides/day: 1 million

**Throughput:**
- Les assume a user performs 5 operation per ride on an average. Hence total requests per day will be 5 millions.
- 5 million reqs per day would be 58 reqs/sec.

**Storage Capacity**
- If each message is of 500 Bytes, hence we need around 2.5 GB of space everyday.
