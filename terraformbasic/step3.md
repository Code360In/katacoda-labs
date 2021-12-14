# breaking the file up

Lets make this easier to read by breaking the single file into multiple

create a providers.tf file to just include a set of providers:

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
```

create a main block for the main terraform resources, ie remove the provider section so that all your have left is:

```sh
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

Now when you run terraform commands, it will run all the files in this block.




