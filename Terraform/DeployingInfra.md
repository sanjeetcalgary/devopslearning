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

<img width="691" alt="image" src="https://user-images.githubusercontent.com/103237142/192302595-e642e96e-8251-4ce3-b852-1c0124bfd525.png">

<img width="692" alt="image" src="https://user-images.githubusercontent.com/103237142/192303174-6fc64624-5821-424c-ba8e-46e02adfd01a.png">

<img width="877" alt="image" src="https://user-images.githubusercontent.com/103237142/192303794-2ef6d3ff-90d8-47de-b6b1-20d60a8678c9.png">

Selective destroy

<img width="889" alt="image" src="https://user-images.githubusercontent.com/103237142/192310927-c273659e-1713-42f4-8270-6ef4e59e7a26.png">

<img width="644" alt="image" src="https://user-images.githubusercontent.com/103237142/192318702-65fbd7dc-1daa-40cb-96dd-64778d61304e.png">

<img width="665" alt="image" src="https://user-images.githubusercontent.com/103237142/192323737-4ff0c74f-2bc0-4224-b800-a41819c7e5a3.png">

$ terraform refresh : will synchonize the current state and desired state

<img width="697" alt="image" src="https://user-images.githubusercontent.com/103237142/192325937-784605c5-a011-4b5f-8f3c-962703923261.png">

<img width="623" alt="image" src="https://user-images.githubusercontent.com/103237142/192326047-7c59e0c1-1690-4b46-95f2-5ff2ac19f6d4.png">

<img width="518" alt="image" src="https://user-images.githubusercontent.com/103237142/192327704-646bb279-dd60-4d22-9107-bcb2f3b04b25.png">

Attributes & O/P values
----------------------------
<img width="627" alt="image" src="https://user-images.githubusercontent.com/103237142/192338630-12c32107-ea86-4708-a001-e7b9c62bdd9e.png">

<img width="692" alt="image" src="https://user-images.githubusercontent.com/103237142/192339528-90276fdc-1aef-44d7-834c-97bdea822be2.png">

<img width="477" alt="image" src="https://user-images.githubusercontent.com/103237142/192342088-26fe6042-4e34-4905-85e8-c3eb170513ab.png">


Referencing cross-resource attribute
----------------------------------------

Variables
----------------------

<img width="333" alt="image" src="https://user-images.githubusercontent.com/103237142/192358823-56a04aa1-c88d-45ee-a63a-a30db39d76bd.png">
























