---
title: "policy_recommendations"
product: "vbgcp"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbgc/guide/policy_recommendations.html"
last_updated: "6/13/2025"
product_version: "7.0.0.47"
---


In this article

Since one backup policy can be used to protect multiple workloads at the same time, it is recommended that you limit the number of processed workloads to simplify the backup schedule and to optimize the backup performance. As a result, you will have have several small policies instead of a big one.

The default limit for simultaneously processed policies is 25 instances per one policy, with 15 sessions running in parallel. These values can be changed in the configuration file /opt/veeam/gcpbackup/ServiceSettings.json.

|  |
| --- |
| { |

Where:

* MaxParallelJobProcesses — the maximum number of simultaneously processed sessions (including policies, restore instance sessions, FLR sessions and so on).
* MaxConcurrentSnapshots, MaxConcurrentInstanceBackups — the maximum number of simultaneously processed VM, Cloud SQL or Cloud Spanner instances per one policy.

Keep in mind that changing these values may induce additional monitoring of the backup appliance resource usage since it may require the machine type of the appliance to be changed to a larger one.

|  |
| --- |
| Important |
| It is not recommended to manually change the default limit for policies processed simultaneously — to adjust the limit, open a [support case](collecting_logs.md). |

Page updated 6/13/2025

Page content applies to build 7.0.0.47
