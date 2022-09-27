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

<img width="484" alt="image" src="https://user-images.githubusercontent.com/103237142/192526158-33bcfd09-bf20-421b-b945-a05188909728.png">

<img width="453" alt="image" src="https://user-images.githubusercontent.com/103237142/192526766-34715f64-7b25-4ff3-ad10-a87ead9ba08d.png">

Through a file

fileName.tfvars

best practise is to have both default and tfvars, tfvars overwrite the default values

+ filename must be **terraform.tfvars**, the variables must be declared in default file as well
+ if the file name is not terraform.tfvars, then we need to explicitly mention the file name

<img width="457" alt="image" src="https://user-images.githubusercontent.com/103237142/192530672-ca7d5f30-f1b7-4094-90a8-077062b0842b.png">

Environment variables:

in windows, in command prompt `setx TF_VAR_<varName> <value>`, you need to change the command prompt session to see the value set

in linux `export TF_VAR_<varName>="value" `

Datatype for variables
---------------------------

<img width="524" alt="image" src="https://user-images.githubusercontent.com/103237142/192532571-151ef2fe-5a4f-4408-b31d-b8c7a74adca2.png">

<img width="481" alt="image" src="https://user-images.githubusercontent.com/103237142/192532707-8c7838fa-43b3-4e9e-8ff8-1d3940ec3a33.png">

<img width="503" alt="image" src="https://user-images.githubusercontent.com/103237142/192533018-69698119-f093-4045-8ce4-917256f455b5.png">

<img width="458" alt="image" src="https://user-images.githubusercontent.com/103237142/192533640-874f2dec-ef88-4bd7-9384-028a8d410a22.png">

a list variable is referenced using index values whereas map variable is referenced using key

Count
---------------------

<img width="514" alt="image" src="https://user-images.githubusercontent.com/103237142/192539387-a713b9d8-ff7f-4331-a5d3-9feff804a50b.png">

<img width="508" alt="image" src="https://user-images.githubusercontent.com/103237142/192539844-834359cb-bba4-4b0e-90ae-0bfd16a26f91.png">

<img width="528" alt="image" src="https://user-images.githubusercontent.com/103237142/192540157-c51098ee-b2fd-40d7-965c-87b0ef1ee928.png">

<img width="431" alt="image" src="https://user-images.githubusercontent.com/103237142/192540693-bcdac16b-9d2b-44c1-b229-3ddb95805fdc.png">

<img width="498" alt="image" src="https://user-images.githubusercontent.com/103237142/192541049-b96e8d98-73c2-4ef1-984a-bf36fb69dc15.png">

Conditional Expression
--------------------------------
<img width="649" alt="image" src="https://user-images.githubusercontent.com/103237142/192544923-442451bc-efac-4ed7-a226-9e1dff84956c.png">

<img width="295" alt="image" src="https://user-images.githubusercontent.com/103237142/192546076-1c933c96-f28a-490e-b96c-1fa0e46f02df.png">

Local Values
-----------------------------
<img width="719" alt="image" src="https://user-images.githubusercontent.com/103237142/192547696-b6229a07-71d9-4dbd-a8bc-a2d7f28b76d5.png">

<img width="678" alt="image" src="https://user-images.githubusercontent.com/103237142/192548338-b2685bbe-cff7-499a-b8d4-4a0d2b32f6ab.png">

<img width="692" alt="image" src="https://user-images.githubusercontent.com/103237142/192548673-d281a513-1a5a-4505-b782-bd544f4e79cb.png">

Functions
---------------------------

<img width="703" alt="image" src="https://user-images.githubusercontent.com/103237142/192593309-c5caed72-6a70-4edf-8814-387b9a63cd36.png">

<img width="699" alt="image" src="https://user-images.githubusercontent.com/103237142/192593419-61e225b6-3066-452e-a480-7229bf72249b.png">

$ terraform console: try out defined functions









































