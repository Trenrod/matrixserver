# Custom Matrix server

## Vision

Keep it as simple as possible regarding deployment, maintainability and implementing [Application Services (AS)](https://matrix.org/docs/guides/application-services)

To achieve this
  - Use official components only
  - No custom code just configuration
  - Automatic rollout of custom applications (AS)

## [Hot to deploy](./deployment/README.md)

## Features

Those are focused features.

### Feature status v1 - Basic features
- [X] Only official docker images are used
- [X] Out of the box synapse deployment
- [X] Automatic TLS generation and renewal with caddy
- [X] Mail support
- [X] Postgres included
- [X] Encrypted audio and video with coturn and certificates (caddy)

### Feature status v1.1 - Refactoring
- [!] Using github Milestones/Projects for status tracking
- [ ] Better certificate generation get rid of workaround for coturn to access caddy certificates
- [ ] TBD...

### Feature status v2 - Feature deployments
- [ ] Application service deployments/updates
- [ ] TBD...

### Feature status v3 - Maintanance
- [ ] CI/CD
- [ ] Backup
- [ ] Monitoring
- [ ] TBD...

### Feature status v4 - Scaling
- [ ] Nomand/Consul
- [ ] Vault
- [ ] TBD...

## Overview

Diagrams made with [C4-PlantUML](https://github.com/plantuml-stdlib/C4-PlantUML) 

### The software system in scope
![context_overview](doc/images/context_diagram.png "Component overview")

###  Containers within the software system in scope
![component_diagram](doc/images/component_diagram.png "Component overview")
