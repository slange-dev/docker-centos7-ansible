# CentOS 7 Ansible Test Image

[![Building](https://github.com/slange-dev/docker-centos7-ansible/actions/workflows/build.yml/badge.svg)](https://github.com/slange-dev/docker-centos7-ansible/actions/workflows/build.yml)
[![Docker pulls](https://img.shields.io/docker/pulls/slangedev/docker-centos7-ansible)](https://hub.docker.com/r/slangedev/docker-centos7-ansible/)
[![Version](https://img.shields.io/docker/v/slangedev/docker-centos7-ansible/latest)](https://hub.docker.com/r/slangedev/docker-centos7-ansible/)
[![Image Size](https://img.shields.io/docker/image-size/slange-dev/docker-centos7-ansible/latest)](https://hub.docker.com/r/slangedev/docker-centos7-ansible/)

CentOS 7 Docker container for Ansible playbook and role testing.

## Tags

  - `latest`: Latest stable version of Ansible, on Python 2.7.x.
  - `python2`: (Deprecated) Same as `latest`, as of early 2020.
  - `python3`: Latest stable version of Ansible, but on Python 3.6.x.

The latest tag is a lightweight image for basic validation of Ansible playbooks. The `testing` tag also includes a comprehensive suite of Ansible and infrastructure testing tools in case you want them pre-installed.

## How to Build

This image is built on Docker Hub automatically any time the upstream OS container is rebuilt, and any time a commit is made or merged to the `master` branch. But if you need to build the image on your own locally, do the following:

  1. [Install Docker](https://docs.docker.com/engine/installation/).
  2. `cd` into this directory.
  3. Run `docker build -t centos7-ansible .`

> Note: Switch between `master` and `testing` depending on whether you want the extra testing tools present in the resulting image.

## How to Use

  1. [Install Docker](https://docs.docker.com/engine/installation/).
  2. Pull this image from Docker Hub: `docker pull slangedev/docker-centos7-ansible:latest` (or use the image you built earlier, e.g. `centos7-ansible:latest`).
  3. Run a container from the image: `docker run --detach --privileged --volume=/sys/fs/cgroup:/sys/fs/cgroup:ro slangedev/docker-centos7-ansible:latest` (to test my Ansible roles, I add in a volume mounted from the current working directory with ``--volume=`pwd`:/etc/ansible/roles/role_under_test:ro``).
  4. Use Ansible inside the container:
    a. `docker exec --tty [container_id] env TERM=xterm ansible --version`
    b. `docker exec --tty [container_id] env TERM=xterm ansible-playbook /path/to/ansible/playbook.yml --syntax-check`

## Notes

I use Docker to test my Ansible roles and playbooks on multiple OSes using CI tools like Jenkins and Travis. This container allows me to test roles and playbooks using Ansible running locally inside the container.

> **Important Note**: I use this image for testing in an isolated environment—not for production—and the settings and configuration used may not be suitable for a secure and performant production environment. Use on production servers/in the wild at your own risk!


## 💛 Support the project

If this project was useful to you in some form, I would be glad to have your support.  It will help to keep the project alive and to have more time to work on Open Source.

The sinplest form of support is to give a ⭐️ to this repo.

You can also contribute with [GitHub Sponsors](https://github.com/sponsors/slange-dev).

[![GitHub Sponsors](https://img.shields.io/badge/GitHub%20Sponsors-Sponsor%20Me-red?style=for-the-badge)](https://github.com/sponsors/slange-dev)

Or if you prefer a one time donation to the project, you can simple:

<a href="https://www.buymeacoffee.com/slange-dev" target="_blank"><img src="https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png" alt="Buy Me A Coffee" style="height: auto !important;width: auto !important;" ></a>
## Author

👤 **slange-dev**

* Website: [https://github.com/slange-dev](https://github.com/slange-dev)
* Github: [@slange-dev](https://github.com/slange-dev)
* 
## Author

Copyright © in 2021 by [slange-dev](https://slange-dev.github.io/).
