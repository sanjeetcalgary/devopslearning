<img width="655" alt="image" src="https://user-images.githubusercontent.com/103237142/192183524-3235e625-5fa4-4b2b-a6b9-f2f676e072ef.png">

https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/ecr_image

https://learn.hashicorp.com/collections/terraform/kubernetes

Authentication and Configuration
--------------------------------------
Configuration for the AWS Provider can be derived from several sources, which are applied in the following order:

1. Parameters in the provider configuration
2. Environment variables
3. Shared credentials files
4. Shared configuration files
5. Container credentials
6. Instance profile credentials and region

The AWS Provider supports assuming an IAM role, either in the provider configuration block parameter `assume_role` or in a `named profile`.

The AWS Provider supports assuming an IAM role using web identity federation and OpenID Connect (OIDC). This can be configured either using environment variables or in a named profile.




