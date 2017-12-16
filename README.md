# ansible-drone-agent

ansible role to install [drone-agent](http://docs.drone.io/installation/).

* [suzuki-shunsuke.drone-agent](https://galaxy.ansible.com/suzuki-shunsuke/drone-agent/)

## Requirements

* Docker Engine
* docker-py

## Role Variables

name | required | default
--- | --- | ---
drone_agent_env | yes | {}
drone_agent_docker_network_name | no | drone
drone_agent_docker_image_name | no | drone/agent
drone_agent_docker_image_tag | no | latest
drone_agent_container_name | no | drone-agent

About `drone_agent_env`, see the following links.

* http://docs.drone.io/installation/
* https://github.com/drone/drone/blob/master/cmd/drone-agent/main.go

## Dependencies

Nothing.

## Example Playbook

```yaml
- hosts: agents
  roles:
    - role: suzuki-shunsuke.drone-agent
      drone_agent_docker_image_tag: 0.8.2
      drone_agent_env:
        DRONE_SERVER: "drone.example.com:9000"
        DRONE_SECRET: "drone-secret"
        DRONE_MAX_PROCS: 4
      become: yes
```

## Change Log

See [CHANGELOG.md](CHANGELOG.md).

## License

[MIT](LICENSE)
