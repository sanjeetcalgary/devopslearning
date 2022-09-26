https://www.terraform.io/language

HashiCorp Terraform is an infrastructure as code tool that lets you define both cloud and on-prem resources in human-readable configuration files that you can version, reuse, and share. You can then use a consistent workflow to provision and manage all of your infrastructure throughout its lifecycle. Terraform can manage low-level components like compute, storage, and networking resources, as well as high-level components like DNS entries and SaaS features.

Working
----------------------
Terraform creates and manages resources on cloud platforms and other services through their application programming interfaces (APIs). Providers enable Terraform to work with virtually any platform or service with an accessible API.

![image](https://user-images.githubusercontent.com/103237142/192278648-19bdc6e1-a5de-4e03-81eb-8a69841aa975.png)

Terraform workflow consists of three stages:

![image](https://user-images.githubusercontent.com/103237142/192278865-1cd8d8ff-3148-4cba-b09d-306d6122e546.png)

+ Terraform supports reusable configuration components called modules that define configurable collections of infrastructure, saving time and encouraging best practices. You can use publicly available modules from the Terraform Registry, or write your own.

Terraform Langugae
------------------------
+ configuration files: Code in the Terraform language is stored in plain text files with the `.tf` file extension. There is also a JSON-based variant of the language that is named with the `.tf.json` file extension.
+ Module: A module is a collection of .tf and/or .tf.json files kept together in a directory.
+ Root module: Terraform always runs in the context of a single root module. A complete Terraform configuration consists of a root module and the tree of child modules (which includes the modules called by the root module, any modules called by those modules, etc.).

**Files & Directories**

+ Terraform normally loads all of the .tf and .tf.json files within a directory and expects each one to define a distinct set of configuration objects. If two files attempt to define the same object, Terraform returns an error.
+ 
