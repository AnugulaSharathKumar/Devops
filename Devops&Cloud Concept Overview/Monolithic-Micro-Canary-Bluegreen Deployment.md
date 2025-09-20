## Monolithic and Micro Service Architecture:
![Bank Downtime Infographic](https://raw.githubusercontent.com/BharathKumarReddy2103/DevOps/main/Day-15/banks-downtime-2025.png.png)

## 🧱 1.Monolithic:
A monolithic application is a single, tightly-coupled codebase (e.g., a 40,000-line Java application packaged into one WAR or JAR file). For one minor changes also it create the new Jar or War file.
If 5 New line code also create the war or jar files. If we face any issue at that time Application face the downtime.
Companies like : SBI , Payment Related back are still following the Monolithic application stategry

## 🧩 2. Microservices with Canary Deployments: Towards Zero Downtime
##MicroService Architecture:
Microservices break large monoliths into **independently deployable components**:

- `Login`, `Payments`, `Transactions`, and `Notifications` can be isolated.
- Developers can deploy only the updated service.
- QE engineers test just the impacted microservice.

### 🕒 Impact on Downtime

Maintenance windows shrink from **30 minutes to 2 minutes**, as only specific services are validated.


### Canary Deployment and Blue Green Deployment

## Canary Deployment:
Even with microservices, achieving zero downtime isn't guaranteed. This is where the **canary deployment model** comes into play:


1. Deploy version `v2` of a microservice alongside existing `v1`.
2. Route **95% traffic to `v1`**, **5% to `v2`**.
3. Internal teams test `v2` live without impacting users.
4. Gradually shift traffic until `v2` handles 100%.

```yaml
# Example of weight-based traffic routing (pseudo-yaml)
canary:
  versions:
    - v1: 95%
    - v2: 5%
````

---

###  Blue-Green Deployments

Some modern banks are adopting **blue-green deployment** strategies:

* Duplicate production environment (green).
* Deploy new version to green.
* Switch the load balancer from **blue to green**.
* Rollback is instantaneous if issues occur.

💰 Blue-green requires **more infrastructure** but ensures zero downtime — ideal for banks with large budgets.
