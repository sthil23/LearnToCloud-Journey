# Phase1-Day4
## What I Learned

- **terraform apply** takes the actions described in a Terramform plan and actually makes the changes to your infrastructure. Whether you're creating new resources, updating existing ones, or tearing things down, this command is what turns your code's "desired state" into reality.

### Two ways to Use **terraform apply**

1. **Automatic Plan Mode**
    - You run **terraform apply** without specifying a plan file.
    - Terraform internally runs **terraform plan** shows you the changes it will make, then asks: "Do you want to perform these actions?"
    - You confirm (or use **-auto-approve** to skip confirmation) and Terraform proceeds to apply those changes.
2. **Saved Plan Mode**
    - First, you explicitly run:
    **"terraform plan -out=myplan.tfplan"**
    This creates a "snapshot" of the steps Terraform will take
    - Then you run:
    **"terraform apply myplan.tfplan"**
    Terraform applies exactly what's in that saved plan, with no extra prompts. This two-step approach is ideal for automation pipelines and CI/CD workflows.
    
    ### **Plan Options**

    Without a saved plan file, **terraform apply** supports all planning modes and planning options available for **terraform plan**.
    - **Planning Modes**: These include **-destroy**, which creates a plan to destroy all remote objects, and **refresh-only**, which creates a plan to update Terraform state and root module output values.
    - **Planning Options**: These include specifying which resource instances Terraform should replace (**-replace**), setting Terraform input variables (**-var** and **-var-file**), etc. 

    ## Common **terraform apply** Options

    - **-auto-approve** Skip the "yes/no" prompt and apply immediately.
    - **input=false** Disable **all** interactive prompts.
    - **-parallelism=n** Limit how many resource operations run in parallel (default is 10).
    - **-lock / -lock=false** Control whether Terraform locks the state file during the apply.
    - **-no-color** Turn off colored output (useful for logs).
    - **-replace=resource** Force replacement of a specific resource instance.
    - **-json** Output results in machine-readable JSON (implies **-input=false** and requires a saved plan or **-auto-approve**)      

### Typical Workflow

1. **terraform init** Prepares your directory, downlaods providers/modules, and configures the backend.
2. **terraform plan** Shows you what will change, without making any real-world updates.
3. **terraform apply** Executes the changes-creating, updating, or deleting cloud resources to match your configuration.