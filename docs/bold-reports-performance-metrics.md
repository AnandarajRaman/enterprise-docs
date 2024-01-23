---
layout: post
title: Performance metrics in Bold Reports On-Premise Edition
description: This section explains the performance metrics for the execution of the same report by multiple users in Bold Reports On-Premise Edition.
platform: report-platform
documentation: ug
keywords: boldreports
canonical: ''
---

# Performance metrics

Performance metrics for the execution of the same report by multiple users.

<table>
 <tr>
    <td>
       <span style="font-weight:bold">Property</span>
    </td>
     <td>
        <span style="font-weight:bold">Value</span>
    </td>
 </tr>
 <tr>
 <td> Users Count </td>
 <td> 100 </td>
 </tr>
 <tr>
 <td> Ramp Up period (seconds) </td>
 <td> 50 </td>
 </tr>
 <td> Loop </td>
 <td> 1 </td>
 </tr>
 <tr>
 <td> Thread Life Time (seconds) </td>
 <td> 700 </td>
 </tr>
 <tr>
 <td> Startup Delay (seconds) </td>
 <td> 2 </td>
 </tr>
 <tr>
 <td> RunTime Controller runtime (seconds) </td>
 <td> 480 </td>
 </tr>
 <tr>
 <td> Flow Control Action Pass Duration (seconds) </td>
 <td> 3 </td>
 </tr>
 </table>

## The performance of each run is shown in the table below

<table>
 <tr>
    <td>
       <span style="font-weight:bold">1st Run</span>
    </td>
     <td>
        <span style="font-weight:bold">2nd Run</span>
    </td>
    <td>
        <span style="font-weight:bold">3rd Run</span>
    </td>
 </tr>
 <tr>
 <td> 100% </td>
 <td> 99.55% </td>
 <td> 99.91% </td>
 </tr>
 </table>

* **Ramp Up period** - The login time period for the test corresponds to half the number of preset users. For instance, if there are 100 users, the ramp-up period would be 50 seconds. This setup allows for two users to log in every second.
* **Loop** - The loop count determines the number of iterations for the testing process.
* **Thread Life Time** - The thread lifetime controls the maximum duration of the entire test. Set the thread lifetime to end the testing after a specific duration, even if issues occur midway through the process.
* **Startup Delay** - Set the startup delay to handle the test's initial delay, preferably around 2 or 3 seconds.
* **RunTime Controller runtime** - The Runtime Controller in JMeter serves as a logic controller enabling you to restrict the execution time of its child elements.
* **Flow Control Action Pass Duration** - Flow Control Action samplers enable us to regulate the speed of requests sent to the server within our test scripts.