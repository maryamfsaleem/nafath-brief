Version: NAFATH-V2
Track: Cybersecurity

## Overview
A reliable 5G service for emergency responders must continue supporting critical communications during congestion, connectivity failures, and cyberattacks. Several IT fields contribute to this goal. Software engineering helps ensure that repeated requests can be handled safely when failures occur. Artificial intelligence can help evaluate predictive models, while offline-first mobile applications allow responders to access information and record updates without a reliable connection. Network slicing can allocate network resources for emergency communications. Cybersecurity incident response helps teams detect attacks, limit damage, and restore affected services. Finally, appropriate data warehouse design allows operators to analyze service usage by region and day. Together, these six areas support service reliability, effective incident management, and informed operational decisions.

## Software
GET, HEAD, OPTIONS and TRACE are considered safe HTTP methods. These methods, along with PUT and DELETE, are also idempotent. Idempotency is important when network or software failures occur because a client may automatically retry a request if it does not receive the server's response. The server may have already processed the request, so using an idempotent method ensures that repeating it has the same intended effect as making it once.
Resource: RFC 9110 - HTTP Semantics - https://www.rfc-editor.org/rfc/rfc9110.html


## AI
Overfitting occurs when a model learns the training data too closely, including noise and outliers. It performs very well on training data but poorly on unseen data. Cross-validation helps detect overfitting by dividing the dataset into several subsets, training the model on some subsets and validating it on the remaining subset. This process is repeated using different subsets, and the validation scores are averaged to estimate the model's performance on new data.
Resource: Cross-validation: evaluating estimator performance - https://scikit-learn.org/stable/modules/cross_validation.html

## Mobile
A responder’s mobile app should remain usable without a reliable connection by displaying locally stored information and saving new reports on the device. When connectivity returns, the app should synchronize pending changes with the server using pull-based requests or push notifications to update data. It should handle synchronization failures, resolve conflicting updates, and prevent duplicate records. This ensures responders can continue working during network outages and that important emergency information is shared accurately once the connection is restored.
Resource: Android Developers - Build an offline-first app - https://developer.android.com/topic/architecture/data-layer/offline-first


## Networking
5G network slicing is a technique that divides a single physical network into multiple virtual slices, each optimized for specific requirements such as bandwidth, latency, and reliability. A dedicated emergency services slice could provide prioritized access to network resources, dedicated bandwidth, and reduced latency for responders during congestion. This would help them maintain critical communications and improve situational awareness during emergencies, although performance still depends on network coverage and available infrastructure.
Resource: 5G Network Slicing Explained: What It Means for First Responder Communications - https://www.premierwireless.com/blog/5g-network-slicing-explained-what-it-means-for-first-responder-communications


## Cybersecurity
The incident response lifecycle has four phases: Preparation, Detection and Analysis, Containment, Eradication and Recovery, and Post-Incident Activity. Preparation establishes response plans, teams, and tools. Detection and Analysis identifies and investigates attacks affecting the 5G service. Containment limits damage by blocking malicious traffic or isolating compromised systems. Eradication removes the threat, and Recovery restores normal operations. Post-Incident Activity reviews the incident and improves security controls to prevent similar attacks.
Resource: SentinelOne - Incident Response Steps & Phases: NIST Framework Explained - https://www.sentinelone.com/cybersecurity-101/services/incident-response-steps-phases/


## Data
A star schema uses denormalized dimension tables connected directly to a central fact table, simplifying queries and reporting. A snowflake schema normalizes dimension tables into related tables, reducing data redundancy but adding complexity and potentially more joins. For reporting daily 5G service usage by region, a star schema is generally more suitable. A central usage fact table connected to Date, Region, and Service dimensions makes it easier to aggregate usage and compare regions over time.
Resource: GeeksforGeeks - Difference between Star Schema and Snowflake Schema - https://www.geeksforgeeks.org/dbms/difference-between-star-schema-and-snowflake-schema/


## Misconception in My Track
A common misconception is that incident response begins only after an attack has been detected. In reality, organizations must prepare beforehand by establishing response plans, assigning responsibilities, and developing procedures for handling incidents. NIST explains that incorporating incident response into cybersecurity risk management can “help organizations prepare for incident responses, reduce the number and impact of incidents that occur, and improve the efficiency and effectiveness of their incident detection, response, and recovery activities.” For a 5G emergency service, preparation helps reduce disruption and protect critical communications.
Resource: NIST - Incident Response Recommendations and Considerations for Cybersecurity Risk Management (SP 800-61 Rev. 3) - https://csrc.nist.gov/pubs/sp/800/61/r3/final


## Open Question
How can a telecom operator contain a cyberattack while keeping critical 5G communications available to emergency responders, especially when isolating compromised systems could disrupt the service?
