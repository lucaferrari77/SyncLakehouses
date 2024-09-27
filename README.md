# Cross-region disaster recovery and business continuity

Disaster recovery (DR) is about recovering from high-impact events, such as natural disasters or failed deployments that result in downtime and data loss. Regardless of the cause, the best remedy for a disaster is a well-defined and tested DR plan and an application design that actively supports DR. Before you begin to think about creating your disaster recovery plan, see Recommendations for designing a disaster recovery strategy.

When it comes to DR, Microsoft uses the [shared responsibility model](https://learn.microsoft.com/en-us/azure/reliability/business-continuity-management-program#shared-responsibility-model). In a shared responsibility model, Microsoft ensures that the baseline infrastructure and platform services are available. At the same time, many Azure services don't automatically replicate data or fall back from a failed region to cross-replicate to another enabled region. For those services, you are responsible for setting up a disaster recovery plan that works for your workload. Most services that run on Azure platform as a service (PaaS) offerings provide features and guidance to support DR and you can use service-specific features to support fast recovery to help develop your DR plan.

For more detailed info, refer to:  </br>
[Reliability in Microsoft Fabric](https://learn.microsoft.com/en-us/azure/reliability/reliability-fabric) </br>
[Azure Reliability](https://learn.microsoft.com/en-us/azure/well-architected/reliability/) </br>
[Micrsoft Fabric - Disaster Recovery Guidance](https://learn.microsoft.com/en-us/fabric/security/experience-specific-guidance?source=recommendations) </br>

# RTO/RPO

RTO, and RPO are key terms used in business continuity and disaster recovery planning:  </br>

 - RTO (Recovery Time Objective): This is the maximum length of time a computer, system, network, or application can be down following a failure. It’s often measured in seconds, minutes, hours, or days. The RTO helps determine the architecture of your systems.  </br>
 - RPO (Recovery Point Objective): This is the maximum amount of data loss that would be acceptable to an organization. Data loss tolerance is often measured in terms of time. The RPO helps you decide on backup frequencies.  </br>

Certain business critical scenarios need very tight RTO and RPO.  </br>
A potential approach might be to use two different environments on two different Azure Regions and this will speed-up the recovery in case of disaster.
You might consider running your processes twice (once per environment) or keeping them in sync by ingesting data from the primary environment to the secondary one as frequently as needed to maintain consistency.


