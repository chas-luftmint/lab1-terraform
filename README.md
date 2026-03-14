# Lab 1: Hardened GCP Infrastructure with Terraform

## Project Overview
Det här projektet automatiserar en deployment av en säker Ubuntu 22.04 LTS VM med Terraform. Inkluderar automatiserade
backup policies och en CI/CD pipeline för säker security linting & validation.
## How to Run
1. **Initialize Terraform:** `terraform init`
2. **Preview Changes:** `terraform plan`
3. **Deploy:** `terraform apply`

## CI/CD Pipeline
Projektet använder GitHub Actions för att säkerställa kod kvalite och säkerhet:
* **Terraform Format:** Håller konsistent styling.
* **Trivy IaC Scan:** Skannar för säkerhets miskonfigurationer.
* **Terraform Validate:** Checkar syntax.


## Infrastructure & Security Decisions
* **Vad gör UFW:** Den är konfigurerad via startup.sh och blockerar all inkommande trafik förutom SSH(port22).
* **Fail2Ban:** Installerad för att förhindra brute-forze attacker.
* **Unattended-Upgrades:** Konfigurerad för att automatiskt installera säkerhets patchar för att minska sårbarheter.
* **Snapshot Policy:** Daglig schemalagd backup som är kopplad till disken med en 7 dagars retention period, för disaster recovery.

## Screenshots
### VM in GCP Console
