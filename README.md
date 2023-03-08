# terraform-ec2-instnace
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 4.16"
    }
  }
  required_version = ">= 1.2.0"
}
provider "aws" {
  region  = "us-east-1"
}
resource "aws_instance" "app_server" {
  ami           = "ami-006dcf34c09e50022"
  instance_type = "t2.micro"
  tags = {
    Name = "myec2instance"