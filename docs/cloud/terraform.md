# Terraform

## Useful Terraform Commands



> TIP: __Get Help__
>
> - Show your Terraform version
> ```bash
> terraform version
> ```
>
> - Get help for commands
> ```bash
> terraform -help
> terraform init -help
> ```

> TIP: __Code Management__
>
> - Format your Terraform code
> ```bash
> terraform fmt
> ```
>
> - Initialize your directory
> ```bash
> terraform init
> ```
>
> - Download and install modules
> ```bash
> terraform get
> ```
>
> - Validate your Terraform code
> ```bash
> terraform validate
> ```

> TIP: __Infrastructure Management__
>
> - Plan your Infrastructure
> ```bash
> terraform plan
> terraform plan -out=tfplan
> ```
>
> - Deploy your Infrastructure
> ```bash
> terraform apply
> terraform apply tfplan
> terraform apply -auto-approve
> ```
>
> - Destroy your infrastructure
> ```bash
> terraform destroy
> terraform destroy -target=aws_instance.example
> ```

> TIP: __State Management__
>
> - View your state file
> ```bash
> terraform show
> terraform state list
> ```
>
> - Refresh the state file
> ```bash
> terraform refresh
> ```
>
> - Manipulate state
> ```bash
> terraform state mv aws_instance.example aws_instance.new
> terraform state rm aws_instance.example
> ```
>
> - Import existing Infrastructure
> ```bash
> terraform import aws_instance.example i-1234567890abcdef0
> ```

> TIP: __Resource Management__
>
> - 'Taint' or 'Untaint' resources
> ```bash
> terraform taint aws_instance.example
> terraform untaint aws_instance.example
> ```
>
> - View outputs
> ```bash
> terraform output
> terraform output instance_ip
> ```

> TIP: __Workspace Management__
>
> - List workspaces
> ```bash
> terraform workspace list
> ```
>
> - Create new workspace
> ```bash
> terraform workspace new dev
> ```
>
> - Switch workspace
> ```bash
> terraform workspace select prod
> ```

> TIP: __Advanced Features__
>
> - Generate dependency diagram
> ```bash
> terraform graph | dot -Tsvg > graph.svg
> ```
>
> - Test expressions
> ```bash
> terraform console
> ```
>
> - Release state lock
> ```bash
> terraform force-unlock LOCK_ID
> ```
>
> - Login to Terraform Cloud
> ```bash
> terraform login
> terraform logout
> ```

> TIP: __Shell Integration__
>
> - Enable tab completion
> ```bash
> terraform -install-autocomplete
> ```