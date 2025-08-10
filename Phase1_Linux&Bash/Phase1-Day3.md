# Phase1-Day3

## What I Learned
- Terraform is an infrastructure as code tool that lets you build, change, and version cloud and on-prem resources safely and efficiently. 
- You write configuration files that describe cloud resources-- like virtual machines, networks, and adatabases-- and Terraform figures out how to create, update, or delete them to match your desired state. 
- Terraform creates and manages resources on cloud platforms and other services through their **application programming interfaces (APIs)**. **Providers** enable Terraform to work with virtually any platform or service with an accessible API.
- Terraform configuration files are **declarative**, meaning that they describe the end state of your infrastructure. You do not need to write step-by-step instructions to create resources because Terraform handles the underlying logic.
- Terraform supports reusable configuration components called **modules** that define configurable collections of infrastructure, saving time and encouraging best practices.
- Terraform workflow consists of three stages:
    - **Write:** You define resources, which may be across multiple cloud providers and services. For example, you might create a configuration to deploy an application on virtual machines in a Virtual Private Cloud (VPC) network with security groups and a load balancer.
    - **Plan:** Terraform creates an execution plan describing the infrastructure it will create, update, or destroy based on the existing infrastructure and your configuration. It also keeps track of your real infrastructure in a **state file**, which acts as a source of truth for your environment. Terraform uses the **state file** to determine the changes to make to your infrastructure so that it will match your configuration.
    - **Apply:** On approval, Terraform performs the proposed operations in the correct order, respecting any resource dependencies. For example. If you update the properties of a VPC and change the number of virtual machines in that VPC, Terraform will recreate the VPC before scaling the virtual machines.
- **terraform init** is always the first command you execute in a new or clone Terraform project. It prepares your working directory by downloading required plugins (providers), installing any referenced modules, and configuring the backend where Terraform stores its state.

## Commands learned (Terraform CLI)

**General Options**
- **input=true|false** Ask for interactive input if needed. Set to **false** to fail instead of prompting
- **-lock=true|false** Enable or disable state file locking during operations.
- **-lock-timeout=\<duration>** How long to wait for a state lock before failing (default 0s).
- **-no-color** Turn off colored output, useful in CI logs
- **-upgrade** Reinstall all providers and modules at their latest acceptable versions.

**Module Source Shortcut**
- **-from-module=MODULE-SOURCE** In an empty directory, copy a configuration from a module source (VCS URL or registry) before initializing.

**Backend-Specific Flags**
- **-backend=false** Skip backend configuration entirely (not recommended if you need remote state)
- **-reconfigure** Ignore existing backend settings and write new ones without migrating state.
- **-migrate-state** Switch to a new backend and copy existing state over, possibly prompting for confirmation.
- **-force-copy** Automatically say "yes" to migrating workspace states and enable **-migrate-state** under the hood.