+++
title = "Architectures"
date = 2019-12-04T09:15:58Z
weight = 5
chapter = true
pre = "<b>X. </b>"
mermaid: true
+++

### Reference Architectures and Design

# How We Design AWS Accounts
{{<mermaid align="left">}}
graph TD;
 
    subgraph 'Master Organisation'
        org_iam(SCP)
        org_iam_template(Template Polices)
        org_iam_config(Cloud Trail)
    end
    org_iam --> shared_iam
    org_iam --> identity_iam
    org_iam --> core_iam
    org_iam  --> route53
    org_iam --> compass_iam
 
    subgraph 'CORE -> Shared Account'
        shared_ami(AMI Building)
        shared_logging(Centralised Logging)
        shared_ad(Active Directory)
        shared_iam(IAM Roles)
    end

    subgraph 'CORE -> Identity'
        identity_iam(IAM Roles)
    end

{{< /mermaid >}}


{{% children  %}}
