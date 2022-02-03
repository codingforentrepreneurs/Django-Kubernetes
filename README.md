[![Django & Kubernetes Logo](https://static.codingforentrepreneurs.com/media/projects/django-kubernetes/images/share/Django__Kubernetes_Tutorial_Series.jpg)](https://www.codingforentrepreneurs.com/projects/django-kubernetes)
# Django & Kubernetes

Learn how to deploy a production-ready Django application into a Kubernetes cluster.

Kubernetes is a tool to manage containers. This type of management is called orchestration because it does more than just manage the containers such as it will scale up and scale down resources as needed (among many other things). 

Since Kubernetes is a massive tool, we're going to be covering a practical implementation using a Docker-based Django application.

Django is a way to build web applications rapidly using Python. There are many ways to get Django into production so the question is why use K8S at all? There's many reasons we'll cover throughout this series but here are a few:

- Gracefully deploy Docker-based Django projects
- Scale up (or scale down) your web apps with ease
- Use a few or a lot of microservices internally or externally
- Self-heal when services go down
- Simplify app deployment (after initial configuration)
- Streamline your backend Infrastructure (provision virtual machines and let k8s do the rest)

Kubernetes can do *a lot* which makes it a great tool to learn but also a daunting one at that. To make it more approachable here's what we'll be doing:

- Start a Python Virtual Environment
- Create a bare bones production-ready Django project 
- Create a Dockerfile to describe our environment (much like [this blog post](https://www.codingforentrepreneurs.com/blog/django-on-docker))
- Use a managed Database service from DitgitalOcean
- Install Kubernetes locally
- Start a Kubernetes Cluster on DigitalOcean
- Provision a Deployment and Service for our Django project
- Implement Github Action Workflows to automate future deployments


### References
- [Django on Docker](https://www.codingforentrepreneurs.com/blog/django-on-docker) guide
- [Docker & Docker Compose](https://www.codingforentrepreneurs.com/projects/docker-and-docker-compose) tutorial series
- [Github Actions](https://www.codingforentrepreneurs.com/blog/django-github-actions) guide
- [DigitalOcean $100 credit](https://do.co/cfe-sh) for new accounts
- [Code](https://github.com/codingforentrepreneurs/Django-Kubernetes)

We have partnered with [DigitalOcean](https://do.co/cfe-sh) to bring you this series. Sign up for an [account](https://do.co/cfe-sh) when you're ready to get started with this series.