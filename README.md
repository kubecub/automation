<h1 align="center" style="border-bottom: none">
    <b>
        <a href="https://docker.nsddd.top">automation</a><br>
    </b>
</h1>
<h3 align="center" style="border-bottom: none">
      ⭐️  Template for a typical module written on Go.  ⭐️ <br>
<h3>


<p align=center>
<a href="https://goreportcard.com/report/github.com/kubecub/automation"><img src="https://goreportcard.com/badge/github.com/kubecub/automation" alt="A+"></a>
<a href="https://github.com/search?q=org%3Akubecub+is%3Aissue+label%3A%22good+first+issue%22+no%3Aassignee&amp;type=issues"><img src="https://img.shields.io/github/issues/kubecub/automation/good%20first%20issue?logo=%22github%22" alt="good first"></a>
<a href="https://github.com/kubecub/automation"><img src="https://img.shields.io/github/stars/kubecub/automation.svg?style=flat&logo=github&colorB=deeppink&label=stars"></a>
<a href="https://github.com/kubecub/automation/blob/main/LICENSE"><img src="https://img.shields.io/badge/license-Apache--2.0-green"></a>
<a href="https://golang.org/"><img src="https://img.shields.io/badge/Language-Go-blue.svg"></a>
</p>

</p>

<p align="center">
    <a href="./README.md"><b>English</b></a> •
    <a href="./README_zh-CN.md"><b>中文</b></a>
</p>

</p>

----

## 🧩 Awesome features

At Github, we want to start new projects faster using best practices with a predefined structure and focusing on core ideas implementation rather than wasting time on environment configuration and copying boilerplate code.

I defined a spec template that I could use to quickly start building a full-fledged project.

In each directory, there is a README.md and an OWNERS, which explains what the directory does and who owns it.

**Labels denger:**
Read about the [automation](https://github.com/kubecub/automation/labels) tag design


## 🛫 Quick start 

> **Note**: You can get started quickly with automation.

1. Generate a [new repository](https://github.com/kubecub/automation/generate) from the template.
2. Clone the repository locally.
3. Update files, read the README files in each directory.
4. Write your code and tests. 

<details>
  <summary>Work with Makefile</summary>

```bash
❯ make help    # show help
❯ make build   # build binary
```

</details>
<details>
  <summary>Work with actions</summary>

Actions provide handling of PR and issue.
We used the bot [🚀@kubbot](https://github.com/kubbot), It can detect issues in Chinese and translate them to English, and you can interact with it using the command `/comment`.

Comment in an issue:

```bash
❯ /intive
```

</details>
<details>
  <summary>Work with Tools</summary>

```bash
❯ make tools
```

</details>
<details>
  <summary>Work with Docker</summary>

```bash
❯ make deploy
```

</details>


## 🕋 architecture diagram
```mermaid
graph LR

subgraph External Services
feishuAPI --> sheetParser
end

subgraph Sheet Parser & Manager
sheetParser[Sheet Parser] --> versionControl
versionControl[Version Control] --> sheetDisplay
end

subgraph Display
sheetDisplay[Sheet Display] --> UI
end

subgraph Backend
versionControl --> API
end

subgraph Frontend
UI[User Interface]
end

API --> UI
UI --> feishuAPI 
```

**MVC Architecture Design:**
```mermaid
graph LR
A[View] -->|1. User interaction| B(Controller)
B -->|2. Requests data| C(Model)
C -->|3. Returns data| B
B -->|4. Updates view| A
```

## 🤖 File Directory Description

Catalog standardization design structure:

```bash
.automation
├── CONTRIBUTING.md          # Contribution guidelines
├── LICENSE                  # License information
├── Makefile                 # Makefile for building and running the project
├── README.md                # Project overview in English
├── README_zh-CN.md          # Project overview in Chinese
├── api                      # API-related files
│   ├── OWNERS               # API owners
│   └── README.md            # API documentation
├── assets                   # Static assets, such as images and stylesheets
│   └── README.md            # Assets documentation
├── build                    # Build-related files
│   ├── OWNERS               # Build owners
│   └── README.md            # Build documentation
├── cmd                      # Command-line tools and entry points
│   ├── OWNERS               # Command owners
│   └── README.md            # Command documentation
├── configs                  # Configuration files
│   ├── OWNERS               # Configuration owners
│   ├── README.md            # Configuration documentation
│   └── config.yaml          # Main configuration file
├── deploy                   # Deployment-related files
│   ├── OWNERS               # Deployment owners
│   └── README.md            # Deployment documentation
├── docs                     # Project documentation
│   ├── OWNERS               # Documentation owners
│   └── README.md            # Documentation index
├── examples                 # Example code and usage
│   ├── OWNERS               # Example owners
│   └── README.md            # Example documentation
├── init                     # Initialization files
│   ├── OWNERS               # Initialization owners
│   └── README.md            # Initialization documentation
├── internal                 # Internal application code
│   ├── OWNERS               # Internal code owners
│   ├── README.md            # Internal code documentation
│   ├── app                  # Application logic
│   ├── pkg                  # Internal packages
│   └── utils                # Utility functions and helpers
├── pkg                      # Public packages and libraries
│   ├── OWNERS               # Package owners
│   ├── README.md            # Package documentation
│   ├── common               # Common utilities and helpers
│   ├── log                  # Log utilities
│   ├── tools                # Tooling and scripts
│   ├── utils                # General utility functions
│   └── version              # Version information
├── scripts                  # Scripts for development and automation
│   ├── LICENSE_TEMPLATES    # License templates
│   ├── OWNERS               # Script owners
│   ├── README.md            # Script documentation
│   ├── githooks             # Git hooks for development
│   └── make-rules           # Makefile rules and scripts
├── test                     # Test files and test-related utilities
│   ├── OWNERS               # Test owners
│   └── README.md            # Test documentation
├── third_party              # Third-party dependencies and libraries
│   └── README.md            # Third-party documentation
├── tools                    # Tooling and utilities for development
│   └── README.md            # Tool documentation
└── web                      # Web-related files, such as HTML and CSS
    ├── OWNERS               # Web owners
    └── README.md            # Web documentation
```

## 🗓️ community meeting

We welcome everyone to join us and contribute to automation, whether you are new to open source or professional. We are committed to promoting an open source culture, so we offer community members neighborhood prizes and reward money in recognition of their contributions. We believe that by working together, we can build a strong community and make valuable open source tools and resources available to more people. So if you are interested in automation, please join our community and start contributing your ideas and skills!

We take notes of each [biweekly meeting](https://github.com/kubecub/automation/issues/2) in [GitHub discussions](https://github.com/kubecub/automation/discussions/categories/meeting), and our minutes are written in [Google Docs](https://docs.google.com/document/d/1nx8MDpuG74NASx081JcCpxPgDITNTpIIos0DS6Vr9GU/edit?usp=sharing).

automation maintains a [public roadmap](https://github.com/kubecub/community/tree/main/roadmaps). It gives a a high-level view of the main priorities for the project, the maturity of different features and projects, and how to influence the project direction.

## 🤼‍ Contributing & Development

kubecub Our goal is to build a top-level open source community. We have a set of standards, in the [Community repository](https://github.com/kubecub/community).

If you'd like to contribute to this automation repository, please read our [contributor documentation](https://github.com/kubecub/automation/blob/main/CONTRIBUTING.md).

Before you start, please make sure your changes are in demand. Discuss proposed changes in the [project discussions](https://github.com/kubecub/automation/discussions), or [report an issue](https://github.com/kubecub/automation/issues) before working on a bug.


## 🚨 License

Automation is licensed under the Apache License, Version 2.0. See [LICENSE](https://github.com/kubecub/automation/tree/main/LICENSE) for the full license text.

[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2Fkubecub%2Fautomation.svg?type=large)](https://app.fossa.com/projects/git%2Bgithub.com%2Fkubecub%2Fautomation?ref=badge_large)


## 🔮 Thanks to our contributors!

<a href="https://github.com/kubecub/automation/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=kubecub/automation" />
</a>
