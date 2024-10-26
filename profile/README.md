### Hello and welcome,

I'm Yaar Naumenko - Cloud Infra Engineer and Solutions Architect.

Please look at the code examples and diagrams of some projects released below. 

[Kubernates (EKS) Essential Platform Tools - scalable and preconfigured Terragrunt configuration](https://github.com/cloudon-one/k8s-platform-tools)
```mermaid
flowchart TD
    subgraph "Infrastructure Layer"
        EKS[EKS Cluster]
        VPC[VPC]
        IAM[IAM Roles/Policies]
    end

    subgraph "Service Mesh & Networking"
        ISTIO[Istio Service Mesh]
        KONG[Kong Ingress]
        DNS[External DNS]
    end

    subgraph "Security & Certificates"
        CERT[Cert Manager]
        SEC[External Secrets]
        style CERT fill:#f9f,stroke:#333
        style SEC fill:#f9f,stroke:#333
    end

    subgraph "Observability"
        LOKI[Loki Stack]
        JAEGER[Jaeger]
        KUBECOST[Kubecost]
        style LOKI fill:#bbf,stroke:#333
        style JAEGER fill:#bbf,stroke:#333
        style KUBECOST fill:#bbf,stroke:#333
    end

    subgraph "Platform Tools"
        ARGO[ArgoCD]
        AIRFLOW[Airflow]
        style ARGO fill:#bfb,stroke:#333
        style AIRFLOW fill:#bfb,stroke:#333
    end

    %% Connections
    EKS --> ISTIO
    EKS --> CERT
    ISTIO --> KONG
    KONG --> DNS
    CERT --> KONG
    SEC --> ARGO
    SEC --> AIRFLOW
    ISTIO --> JAEGER
    LOKI --> KUBECOST
```


[Kubernates (EKS) ready to use Terraform modules](https://github.com/cloudon-one/k8s-platform-modules)
```mermaid
graph TB
    subgraph Core["Core Infrastructure"]
        karpenter["Karpenter<br/>(Node Management)"]
        istio["Istio<br/>(Service Mesh)"]
    end

    subgraph Security["Security & Certificates"]
        certm["Cert Manager<br/>(Certificate Management)"]
        extsec["External Secrets<br/>(Secrets Management)"]
    end

    subgraph Ingress["Ingress & DNS"]
        kong["Kong Gateway<br/>(API Gateway)"]
        extdns["External DNS<br/>(DNS Management)"]
    end

    subgraph Observability["Observability Stack"]
        loki["Loki Stack<br/>(Logging)"]
        jaeger["Jaeger<br/>(Tracing)"]
        kubecost["Kubecost<br/>(Cost Management)"]
    end

    subgraph DevOps["DevOps Tools"]
        argocd["ArgoCD<br/>(GitOps)"]
        airflow["Airflow<br/>(Workflow Management)"]
    end

    %% Core connections
    istio --> kong
    istio --> jaeger
    karpenter --> Core

    %% Security connections
    certm --> kong
    extsec --> DevOps
    extsec --> Observability

    %% Ingress connections
    kong --> extdns
    
    %% Observability connections
    loki --> Observability
    jaeger --> Observability
    kubecost --> Observability

    %% DevOps connections
    argocd --> Core
    argocd --> Security
    argocd --> Ingress
    argocd --> Observability
    airflow --> Core

    classDef default fill:#f9f9f9,stroke:#333,stroke-width:2px
```

[AWS Multi-Account Landing Zone with Terragrunt and Terraform](https://github.com/cloudon-one/aws-terragrunt-configuration)
![aws-terragrunt-lz](https://github.com/cloudon-one/aws-terragrunt-configuration/blob/main/aws/aws-landing-zone.png)

[Multi-tenant, scalable and isolated GCP Cloud Landing Zone](https://github.com/cloudon-one/snippet)
![gcp snippet](https://github.com/cloudon-one/snippet/blob/main/GCP%20HLD%20-%20SNIPPET-GCP.png)

[AWS FinOps Idle Resources Cleaner](https://github.com/cloudon-one/aws-cleaner)

![aws cleaner hld](https://github.com/cloudon-one/aws-cleaner/blob/main/image_original.jpeg)

[GCP FinOps Resources Recommender](https://github.com/cloudon-one/gcp-finops-recommender)
![gcp finops](https://github.com/cloudon-one/gcp-finops-recommender/blob/main/image_fixed_width.png)

[OpenAI applications samples -  API, AI assistant and vision](https://github.com/cloudon-one/genai)

[DevSecOps Best Practices and resources](https://github.com/cloudon-one/DevSecOps)

[List of selected k8s resources](https://github.com/cloudon-one/k8s-resources)

[Cloud DevOps Essentials](https://github.com/cloudon-one/devops-toolset) 

[HCP Vault on GCP and AWS terraform template](https://github.com/cloudon-one/vault)

[GCP terraform resources](https://github.com/cloudon-one/gcp-terraform-resources) 

[AWS terraform resources](https://github.com/cloudon-one/aws-tf-modules) 


