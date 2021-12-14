# run a cdk


`mkdir learn-terraform-docker-container`{{execute}}    

`cd learn-terraform-docker-container`{{execute}}   

`nano main.tf`{{execute}}   
copy the code below

`terraform init`{{execute}}    

`terraform plan`{{execute}}    

`terraform apply`{{execute}}    

note the new terraform state file

`tree`{{execute}}

`terraform state list`{{execute}}

`terraform state show`{{execute}}

check running containers
`docker ps`{{execute}}   

open 8000

lets generate a graph

`terraform graph | dot -Tpng > graph.png`{{execute}}


```sh
terraform {
  required_providers {
    docker = {
      source  = "kreuzwerker/docker"
      version = "~> 2.13.0"
    }
  }
}

provider "docker" {}

resource "docker_image" "nginx" {
  name         = "nginx:latest"
  keep_locally = false
}

resource "docker_container" "nginx" {
  image = docker_image.nginx.latest
  name  = "tutorial"
  ports {
    internal = 80
    external = 8000
  }
}
```