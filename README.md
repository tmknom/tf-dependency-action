# tf-dependency-action

Identify the Terraform state directories that use the specified modules.

<!-- actdocs start -->

## Description

This action discovers the Terraform state directories that use the specified local modules.
A "state directory" is where you run `terraform plan` or `terraform apply`.
It usually contains the `terraform.tfstate` file.

For example, if you modify a Terraform local module, you can see which state directories are affected.
With this action, you can easily identify relationships in your Terraform configurations,
making it easier to manage changes and understand their impacts.

## Usage

```yaml
  steps:
    - name: Tf dependency
      uses: tmknom/tf-dependency-action@v0
      with:
        modules: module/foo,module/bar
```

## Inputs

| Name | Description | Default | Required |
| :--- | :---------- | :------ | :------: |
| base-dir | The base directory that contains the state directories and module directories. | `${{ github.workspace }}` | no |
| modules | Paths of files or directories that might be Terraform modules. | n/a | no |

## Outputs

| Name | Description |
| :--- | :---------- |
| dirs | The state directories that use the specified modules. |

<!-- actdocs end -->

## Permissions

N/A

### Requirements

- [Terraform](https://www.terraform.io/)

## FAQ

N/A

## Related projects

- [tfmod](https://github.com/tmknom/tfmod): Explore the dependencies and dependents for Terraform.

## Release notes

See [GitHub Releases][releases].

[releases]: https://github.com/tmknom/tf-dependency-action/releases
