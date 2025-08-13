# Terraform Commands

1. **terraform init** Prepares a working directory for Terraform:
    - Downloads provider plugins
    - Installs referenced modules
    - Configures the backend for state storage
2. **terraform plan** Shows you what Terraform will change without doing anything yet:
    - Compares current real-world infrastructure to your code
    - Outputs a plan of create/update/delete actions
    - Can be saved to a file (e.g. **terraform plan -out=plan.tfplan**)
3. **terraform apply** Actually makes the changes to match your code:
    - Reads a saved plan file (if provided) or auto-runs a plan
    - Prompts you to confirm (unless **-auto-approve**)
    - Creates, updates, or destroys resources as specified
4. **Common Flags**
    - **-auto-approve**: Skip approval prompt on **apply**
    - **-input=false**: Disable interactive prompts
    - **-upgrade**: On **init**, upgrade all providers/modules to their newest allowed versions
    - **-parallelism=N**: On **apply**, limit concurrent operations (default 10)
    - **-no-color**: Turn off colored output (useful in CI)