<div align="center">

# Cliff Gita

### DevOps & Cloud Engineer · AWS · Terraform · Kubernetes · DevSecOps

I build secure, automated and observable cloud platforms, and ship them through CI/CD pipelines that check every change before it reaches production.

<p>
  <a href="https://www.linkedin.com/in/cliff-gita"><img src="https://img.shields.io/badge/LinkedIn-Cliff%20Gita-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" /></a>
  <a href="mailto:gitacliff48@gmail.com"><img src="https://img.shields.io/badge/Email-gitacliff48%40gmail.com-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Email" /></a>
  <a href="https://www.youtube.com/watch?v=PMeldVsWBpc"><img src="https://img.shields.io/badge/Demo-Serverless%20Walkthrough-FF0000?style=for-the-badge&logo=youtube&logoColor=white" alt="Serverless platform demo walkthrough" /></a>
</p>

</div>

---

## About me

- DevOps engineer with **6+ years in open-source digital health** and **420+ merged pull requests**.
- **OpenMRS Platform 2.4 Release Manager** and **OpenMRS Fellow (2020/21)**, working on FHIR, PLIR and the analytics engine.
- Software engineer at the **Digital Initiatives Group, University of Washington** (2022–2025), working on OpenELIS Global and Community Health Toolkit.
- Today I focus on **AWS infrastructure as code, Kubernetes, DevSecOps pipelines and observability**.
- Based in Kampala, Uganda · open to remote DevOps and cloud roles.

---

## Featured projects

| Project | What it shows | Stack |
|---|---|---|
| [**AWS Serverless Web Platform**](https://github.com/gitcliff/aws-serverless-web-platform) · [demo](https://www.youtube.com/watch?v=PMeldVsWBpc) | Six-tier production app built entirely in Terraform. Deploys through GitHub Actions OIDC with no long-lived AWS keys. WAF on the edge, plus X-Ray tracing, CloudWatch alarms, Synthetics canaries and SLOs. | Terraform · Lambda · API Gateway · DynamoDB · CloudFront · WAF · Route 53 |
| [**Microservices DevOps Stack**](https://github.com/gitcliff/microservices-devops-stack) | 7 containerized services deployed to Kubernetes, with Prometheus and Grafana in the cluster. Every PR passes 9 security and quality checks, and every image ships with an SBOM and a vulnerability scan before it is published. | Kubernetes · Docker · GitHub Actions · Trivy · Semgrep · Snyk · SonarQube |
| [**Ubuntu Cloud Support Lab**](https://github.com/gitcliff/ubuntu-cloud-support-lab) | Reproducible break/fix labs for systemd, DNS, LVM, apt and LXD networking, each with a root-cause write-up. Includes a diagnostics script tested in CI. | Linux · Bash · bats · ShellCheck · Multipass/LXD |
| [**Jenkins CI/CD Automation**](https://github.com/gitcliff/Build-Automation-CICD-with-Jenkins) | Declarative and multibranch pipelines, shared libraries, webhooks, automatic versioning, and Docker image builds pushed to Docker Hub and Nexus. | Jenkins · Groovy · Maven · Docker · Nexus |
| [**Nexus Artifact Management**](https://github.com/gitcliff/Artifact-Repository-Manager-with-Nexus-Projects) | Running Nexus on a cloud server: publishing artifacts, using the REST API and managing blob stores. | Nexus · Maven · Gradle · DigitalOcean |
| [**3-Tier App on EKS**](https://github.com/gitcliff/3-Tier-app-on-eks) *(in progress)* | Flask and React app with security-first CI, being prepared for deployment to Amazon EKS. | Python · React · PostgreSQL · Docker · EKS |

---

## How I ship code

The pipeline in [microservices-devops-stack](https://github.com/gitcliff/microservices-devops-stack/tree/main/.github/workflows): untrusted PR code never sees registry credentials, and only scanned images get published.

```mermaid
flowchart LR
    PR[Pull request] --> G{PR gate}
    G --> S1[Gitleaks<br/>secrets]
    G --> S2[Trivy<br/>files + images]
    G --> S3[Semgrep<br/>SAST]
    G --> S4[Snyk<br/>dependencies]
    G --> S5[SonarQube<br/>quality + coverage]
    G --> S6[Unit + smoke<br/>tests]
    S1 & S2 & S3 & S4 & S5 & S6 --> M[Merge to main]
    M --> B[Build image + SBOM]
    B --> V{Critical CVEs?}
    V -->|yes| X[Block]
    V -->|no| P[Push to Docker Hub<br/>by SHA + digest]
```

Every job runs with least-privilege permissions, third-party actions are pinned to commit SHAs, and scan results go to GitHub code scanning.

---

## Tech stack

**Cloud & IaC**

<p>
  <img src="https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonwebservices&logoColor=white" alt="AWS" />
  <img src="https://img.shields.io/badge/Terraform-7B42BC?style=flat-square&logo=terraform&logoColor=white" alt="Terraform" />
  <img src="https://img.shields.io/badge/Ansible-EE0000?style=flat-square&logo=ansible&logoColor=white" alt="Ansible" />
  <img src="https://img.shields.io/badge/DigitalOcean-0080FF?style=flat-square&logo=digitalocean&logoColor=white" alt="DigitalOcean" />
</p>

**Containers & CI/CD**

<p>
  <img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white" alt="Docker" />
  <img src="https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white" alt="Kubernetes" />
  <img src="https://img.shields.io/badge/GitHub%20Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white" alt="GitHub Actions" />
  <img src="https://img.shields.io/badge/Jenkins-D24939?style=flat-square&logo=jenkins&logoColor=white" alt="Jenkins" />
  <img src="https://img.shields.io/badge/GitLab%20CI-FC6D26?style=flat-square&logo=gitlab&logoColor=white" alt="GitLab CI" />
  <img src="https://img.shields.io/badge/Nexus-1B1C30?style=flat-square&logo=sonatype&logoColor=white" alt="Nexus" />
</p>

**DevSecOps**

<p>
  <img src="https://img.shields.io/badge/Trivy-1904DA?style=flat-square&logo=aqua&logoColor=white" alt="Trivy" />
  <img src="https://img.shields.io/badge/Gitleaks-555555?style=flat-square" alt="Gitleaks" />
  <img src="https://img.shields.io/badge/Semgrep-2D3748?style=flat-square&logo=semgrep&logoColor=white" alt="Semgrep" />
  <img src="https://img.shields.io/badge/Snyk-4C4A73?style=flat-square&logo=snyk&logoColor=white" alt="Snyk" />
  <img src="https://img.shields.io/badge/SonarQube-4E9BCD?style=flat-square&logo=sonarqube&logoColor=white" alt="SonarQube" />
  <img src="https://img.shields.io/badge/CycloneDX%20SBOM-555555?style=flat-square" alt="CycloneDX SBOM" />
</p>

**Observability**

<p>
  <img src="https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white" alt="Prometheus" />
  <img src="https://img.shields.io/badge/Grafana-F46800?style=flat-square&logo=grafana&logoColor=white" alt="Grafana" />
  <img src="https://img.shields.io/badge/CloudWatch-FF4F8B?style=flat-square&logo=amazoncloudwatch&logoColor=white" alt="CloudWatch" />
  <img src="https://img.shields.io/badge/X--Ray-232F3E?style=flat-square&logo=amazonwebservices&logoColor=white" alt="AWS X-Ray" />
</p>

**Linux, languages & tools**

<p>
  <img src="https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black" alt="Linux" />
  <img src="https://img.shields.io/badge/Bash-4EAA25?style=flat-square&logo=gnubash&logoColor=white" alt="Bash" />
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python" />
  <img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white" alt="TypeScript" />
  <img src="https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white" alt="Java" />
  <img src="https://img.shields.io/badge/Nginx-009639?style=flat-square&logo=nginx&logoColor=white" alt="Nginx" />
  <img src="https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white" alt="Git" />
</p>

---

## Open-source contributions

| Community | Role | Highlights |
|---|---|---|
| [OpenMRS](https://openmrs.org) | [Platform 2.4 Release Manager](https://talk.openmrs.org/t/platform-2-4-release-manager-cliff-gita/29566) · [Fellow 2020/21](https://talk.openmrs.org/t/my-fellowship-journey-cliff-gita/31148) · Contributor since 2019 | 110+ merged PRs across openmrs-core, the FHIR2 module, O3 microfrontends and distribution packaging |
| [DIGI, University of Washington](https://digi.uw.edu) | Software Engineer (2022–2025) | 220+ merged PRs to OpenELIS Global 2 and Community Health Toolkit apps; built OE Watchdog, a Prometheus/Grafana monitoring stack |

---

## Currently

- 🔭 Taking the Kubernetes deployment further: Helm charts and GitOps with Argo CD
- 🚀 Deploying the 3-tier app to Amazon EKS with Terraform
- 📚 Preparing for AWS certification

---

<div align="center">

<img src="https://streak-stats.demolab.com?user=gitcliff&theme=default&hide_border=true" alt="GitHub contribution streak" />

<br/>

**Build · Automate · Secure · Observe**

</div>
