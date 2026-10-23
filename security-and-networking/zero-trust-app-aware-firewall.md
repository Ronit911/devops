
# Zero Trust and Application-Aware Firewall

## Overview

This document covers my learning around Zero Trust security principles and application-aware access controls, including restricting which applications or websites can access the internet.

The goal is to understand how access policies work, what they control, and how to verify that the intended restrictions are being enforced.

## What Is Zero Trust?

Zero Trust is a security approach based on the principle that access should not be trusted automatically just because a user or device is connected to a particular network.

Access decisions should be based on the relevant identity, device, resource, and policy requirements.

The exact checks depend on the security product and its configuration.

## What Is an Application-Aware Firewall?

An application-aware firewall or access-control system can use application identity or other traffic characteristics to make access decisions.

Depending on the product, policies may allow or restrict selected applications, destinations, or types of traffic.

For example, an organization might want to:

- Allow required work applications.
- Restrict selected websites or applications.
- Apply different access rules to different users or devices.
- Inspect policy decisions and troubleshoot blocked connections.

The actual capabilities depend on the product, operating system, and traffic path.

## How Access Policies Work

A simplified flow is:

```text
Application Generates Traffic
             |
             v
Traffic Passes Through
Configured Security Controls
             |
             v
Policy Evaluation
       /           \
      v             v
   Allowed        Blocked
      |             |
      v             v
Destination      Connection
Reachable        Restricted
```

The diagram is conceptual. Real products may evaluate multiple policies and use different enforcement mechanisms.

## Testing the Policy

To verify a configuration:

1. Identify the device and the security product enforcing the policy.
2. Record the intended allowed applications and destinations.
3. Record the intended restricted applications and destinations.
4. Apply the relevant access rules.
5. Test an allowed application or destination.
6. Test a restricted application or destination.
7. Review the available logs or policy status.
8. Check whether the result matches the intended policy.
9. Investigate unexpected results instead of assuming the policy is working.

## Important Distinctions

### DNS Filtering

DNS filtering can restrict access by controlling the resolution of domain names.

It does not, by itself, guarantee that every connection to a service is blocked through every possible route.

### Network Firewall Rules

Traditional firewall rules commonly use network addresses, protocols, ports, and connection state.

They are different from application-identity-based controls.

### Application-Aware Controls

Application-aware controls attempt to identify and apply rules to particular applications or traffic categories. Their effectiveness depends on how the product identifies traffic and enforces its policy.

These mechanisms can complement each other, but they should not be treated as interchangeable.

## Troubleshooting

If an application or website behaves unexpectedly, check:

- Is the correct policy enabled?
- Is the policy applied to the intended device or user?
- Does the product identify the traffic as expected?
- Is the traffic passing through the enforcement point?
- Are DNS resolution and routing working as expected?
- Are other policies affecting the result?
- Do the logs indicate an allow or block decision?
- Does the behavior differ between applications or connection paths?

Only test alternative paths that are within your authorization and control.

## What I Learned

- Zero Trust is a broader security approach, not just a single firewall setting.
- Different access-control mechanisms enforce policies at different layers.
- A successful blocked-website test does not prove that all traffic to that service is blocked.
- Policy scope, traffic identification, and enforcement points matter.
- Logs and repeatable tests are important for verifying security behavior.

## Notes From My Setup

- Security product and version: To be documented
- Operating system: To be documented
- Intended allowed applications or destinations: To be documented
- Intended restricted applications or destinations: To be documented
- Results of allowed and blocked tests: To be documented
- Issues encountered and their resolution: To be documented

## Security Considerations

Use the minimum access required for the intended task. Verify that required services remain available, and do not claim that a device is fully secured based on a small number of successful tests.
