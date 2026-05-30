# Cloud Basics (AWS or Azure) — Resume Booster

Service MNCs are doubling down on cloud (TCS Cloud, Infosys Cobalt, etc.). A line of cloud awareness on your resume **separates you from 70% of freshers**.

Goal: pass **AWS Certified Cloud Practitioner (CLF-C02)** *or* **Azure Fundamentals (AZ-900)** — both are entry-level, non-technical, ~3-4 weeks of evening prep.

> Either one is fine for placement. Pick AWS if you want the more popular cert; Azure if your college / interest leans Microsoft.

## Why this works for placements

- Both certs are **explicitly mentioned** in many TCS / Infosys / Wipro JDs.
- Certified freshers often get fast-tracked into **cloud / DevOps internal training**.
- The exam is ~$100 USD; many colleges have campus voucher discounts.

## AWS Cloud Practitioner — syllabus you must know

1. **Cloud concepts** — what cloud is, 6 advantages (pay-as-you-go, elasticity, agility, global, no CapEx, focus on business).
2. **Deployment & service models** — IaaS, PaaS, SaaS; public / private / hybrid cloud.
3. **AWS global infrastructure** — Regions, Availability Zones (AZs), Edge Locations.
4. **Core compute** — EC2 (instance types, pricing), Lambda (serverless), Elastic Beanstalk, ECS/EKS (concept).
5. **Storage** — S3 (object), EBS (block), EFS (file), Glacier (archive).
6. **Networking** — VPC, subnets, security groups, Route 53 (DNS), CloudFront (CDN).
7. **Databases** — RDS (relational), DynamoDB (NoSQL), Redshift (warehouse), Aurora.
8. **Security & identity** — IAM users, roles, policies; shared responsibility model; MFA; KMS.
9. **Monitoring & management** — CloudWatch (logs/metrics), CloudTrail (audit), Trusted Advisor.
10. **Pricing & support** — Free tier, billing alarms, Cost Explorer, support plans (Basic → Enterprise).

## Hands-on (free tier)

Sign up at aws.amazon.com (credit card needed for verification but **set a $0 alarm**).

Mini exercises (each ~30 min):
1. Launch and SSH into an EC2 t2.micro Linux instance. Stop & terminate.
2. Create an S3 bucket and upload a file. Make it public, fetch via URL, then make private again.
3. Create a Lambda function (Python) that returns `"hello"` and test it.
4. Set up an IAM user with read-only S3 access and verify.
5. Create a billing alarm at $1 to learn CloudWatch.

> **Always terminate** what you create — free tier limits are tight.

## Resources

- **AWS Skill Builder** — free official courses for CCP.
- **freeCodeCamp** — "AWS Certified Cloud Practitioner Full Course" (~14h YouTube).
- **Stephane Maarek** course on Udemy — paid, but high quality (often discounted).
- **Tutorials Dojo** — best practice tests (paid, worth it).

## 4-week plan

| Week | Focus                                                                |
| ---- | -------------------------------------------------------------------- |
| 1    | Cloud concepts, AWS global infra, free tier signup.                  |
| 2    | Compute (EC2, Lambda), Storage (S3, EBS).                            |
| 3    | Networking (VPC, R53), Databases (RDS, DynamoDB), IAM.               |
| 4    | Pricing, billing, monitoring; full mock exams, schedule the test.    |

## Resume bullet

```
AWS Certified Cloud Practitioner (or "in progress; exam scheduled") —
Familiar with EC2, S3, IAM, Lambda, VPC, CloudWatch; hands-on with
free-tier deployments.
```

## Alternative: Azure Fundamentals (AZ-900)

Almost identical syllabus but in Microsoft's vocabulary:
- Azure VMs, App Services, Azure Functions.
- Blob Storage, Disk Storage.
- Azure SQL, Cosmos DB.
- Microsoft Entra ID (formerly Azure AD).
- Pricing calculator.

Microsoft offers **free practice + sometimes free exam vouchers via Microsoft Learn Cloud Skills Challenge** events — watch for those.

## Don't go too deep

You're not preparing to be a cloud engineer. For placement, you need:
- *Vocabulary* (regions, AZs, EC2, IAM, S3, VPC).
- *One project* on the cloud (e.g., your Flask app deployed on EC2 or as a Lambda).
- *Awareness* of pricing / shared responsibility.

That's enough to confidently say "yes, I have hands-on AWS" in an interview.
