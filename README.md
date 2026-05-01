# Cobalt Strike 4.9 Package Overview

This repository contains the package layout and bundled files I have for Cobalt Strike 4.9.

## About

I organized this repository into client-side and server-side components along with a few bundled support files so the contents are easier to inspect.

I am using this README as a repository overview. It explains what is included here and what can be inferred from the packaged scripts, without turning the page into an operational guide.

## Repository Structure

```text
.
|-- Client/
|   |-- cobaltstrike-client.cmd
|   |-- cobaltstrike-client.jar
|   |-- cobaltstrike-client.sh
|   |-- cobaltstrike.auth
|   `-- uHook.jar
|-- Server/
|   |-- TeamServerImage
|   |-- c2lint
|   |-- cobaltstrike.auth
|   |-- source-common.sh
|   |-- teamserver
|   `-- third-party/
|       |-- README.winvnc.txt
|       |-- winvnc.x64.dll
|       `-- winvnc.x86.dll
`-- cobaltstrike_4.9.jpeg
```

## Included Components

### Client

The `Client/` directory contains Java-based launch assets for the graphical client:

- `cobaltstrike-client.jar`
- `cobaltstrike-client.cmd`
- `cobaltstrike-client.sh`
- `uHook.jar`
- `cobaltstrike.auth`

From the launcher scripts, the client is started through Java and references `uHook.jar` as a Java agent.

### Server

The `Server/` directory contains the server-side launcher and runtime assets:

- `teamserver`
- `TeamServerImage`
- `c2lint`
- `source-common.sh`
- `cobaltstrike.auth`

From what I reviewed, the `teamserver` script is a Bash wrapper that checks for Java tooling, checks for elevated execution on Linux, and references a local Java keystore for SSL/TLS.

### Third-Party Files

The `Server/third-party/` directory includes VNC-related DLLs and an upstream README/license notice:

- `winvnc.x86.dll`
- `winvnc.x64.dll`
- `README.winvnc.txt`

## Environment Notes

Based on the included scripts, this package appears to expect:

- Java installed and available on `PATH`
- `keytool` available on `PATH`
- A Unix-like shell environment for the `Server/teamserver` launcher
- Linux superuser privileges for the server launcher path shown in the script

These are descriptive observations from the repository contents, not setup instructions.

## Files Reviewed

I prepared this README after reviewing:

- [Client/cobaltstrike-client.cmd](D:\Resource\CobaltSrike_4.9.1_Cracked_Pwn3rzs\Client\cobaltstrike-client.cmd)
- [Client/cobaltstrike-client.sh](D:\Resource\CobaltSrike_4.9.1_Cracked_Pwn3rzs\Client\cobaltstrike-client.sh)
- [Server/teamserver](D:\Resource\CobaltSrike_4.9.1_Cracked_Pwn3rzs\Server\teamserver)
- [Server/source-common.sh](D:\Resource\CobaltSrike_4.9.1_Cracked_Pwn3rzs\Server\source-common.sh)
- [Server/third-party/README.winvnc.txt](D:\Resource\CobaltSrike_4.9.1_Cracked_Pwn3rzs\Server\third-party\README.winvnc.txt)

## Security And Legal Notice

- Offensive security software must only be handled in explicitly authorized environments.
- Unauthorized or cracked software may violate law, licensing terms, and organizational policy.
- If you need a legitimate red-team platform, use a properly licensed and vendor-supported distribution.

## Scope Of This README

I am intentionally not including:

- deployment instructions
- startup steps
- connection instructions
- payload or post-exploitation guidance
- operational usage examples
