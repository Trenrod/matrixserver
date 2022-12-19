# Custom Matrix server

This repo is my personal playground to deploy, maintain and configure matrix servers for private usage.

## Milestone 1

### Overview

```plantuml
!define ICONURL https://raw.githubusercontent.com/tupadr3/plantuml-icon-font-sprites/v2.4.0
!includeurl ICONURL/devicons2/postgresql.puml 
!includeurl ICONURL/devicons2/github_original.puml

!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/master/C4_Container.puml

Person(enduser, "End-User", "Matrix user. Consumes matrix over a client.")

Person(developer, "Developer", "Creates and extends features for this matrix instance.")
 
Person(admin, "Administrator", "Provisioning and maintaining this matrix instance and its users.")

System_Boundary(vm, "Virutal machine") {
    Container(caddy2, "Caddy2", "Caddy2, Docker, TLS, Certificates", "Reverse proxy. Redirects to internal containers. Creates and renews certificates.")
    Container(matrix, "Matrix server", "Matrix, Synapse, Docker, Python3", "Synapse a Matrix server implementation.")
    Container(postgresql, "PostgreSql DB", "Matrix, Synapse, Docker, Python3", "Synapse a Matrix server implementation.", $sprite="postgresql")

    Rel(matrix, postgresql, "persists data", "tcp")
    Rel(caddy2, matrix, "forwards requests", "http")
}

System(dev, "Jump server") {
    Container(ansible, "Ansible", "Ansible, Python3", "Deployment scripts.")
}

System_Ext(github, "Github", "Souce code hosted on github", $sprite="github_original")
System_Ext(mail, "Mail Server", "Mail server to send mails")

Rel(enduser, caddy2, "Interact with matrix client interface", "https")
Rel(admin, caddy2, "Interact with matrix admin interface", "https")
Rel(developer, github, "Commit changes", "https, ssh")

Rel(ansible, github, "Fetches sourcecode", "https")

Rel(admin, ansible, "Triggers deployments", "ssh")

Rel(ansible, vm, "Deploys and updates components", "ssh")

Rel(matrix, mail, "Sends mails", "smtp")

```

## Setup

### Deployment

see [Deployment](./Deployment/README.md)

### Add or update new features

TBD

### Backups

TBD
