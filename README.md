<p align="center">
  <img src="./assets/x1-tivimate-hero.svg" alt="X1 TiviMate Community" width="100%" />
</p>

<p align="center">
  <strong>PUBLIC · COMMUNITY · SELF-HOSTED</strong><br>
  Device control for compatible TiviMate-based deployments.
</p>

<p align="center">
  <a href="https://x1panel.space"><strong>WEBSITE</strong></a>
  &nbsp;·&nbsp;
  <a href="https://forum.x1panel.space"><strong>FORUM</strong></a>
  &nbsp;·&nbsp;
  <a href="https://discord.gg/vSSw6jHmw"><strong>DISCORD</strong></a>
  &nbsp;·&nbsp;
  <a href="https://t.me/+XkuQS_QuD6g4Nzc0"><strong>TELEGRAM</strong></a>
</p>

---

## X1 TiviMate Community

**X1 TiviMate Community is a standalone public X1 project for managing compatible TiviMate-based deployments.**

> **Free means functional.**
> The public release is intended to be useful as released and can be self-hosted independently.

This project is separate from X1's private commercial platforms. Public community software and private commercial systems are different products with different operating scopes.

---

<p align="center">
  <img src="./assets/x1-tivimate-control-loop.svg" alt="X1 TiviMate control loop" width="100%" />
</p>

## What it controls

- Portal configuration
- Device registry and online/offline visibility
- Welcome and runtime configuration
- Announcements and device messages
- QR pairing
- X1 Device Agent enrollment
- Authenticated device heartbeat and capability reporting
- Conservative remote actions such as configuration sync, message delivery and update checks
- Audit logging
- Secure administrator authentication
- Optional TOTP two-factor authentication

---

## Operating model

`ENROLL` → `PAIR` → `SYNC / MESSAGE / UPDATE CHECK` → `DEVICE REPORTS STATE` → `VERIFY`

> **A command being sent is not the same as a command being proven successful.**

The device agent supports authenticated device communication and a deliberately conservative public command surface. For production use, verify the resulting state on the actual compatible application/device build.

---

## Runtime truth / compatibility

This repository targets **compatible TiviMate-based Android deployments** tested against the integration surface provided by the project.

Application behavior can vary between builds. A feature existing in the panel does not prove that every historical or third-party APK implements that feature at runtime.

For real deployment confidence:

1. configure the panel;
2. pair a real device;
3. exercise the required action;
4. verify the resulting state on the device.

Implementation details that exist only for binary compatibility with older compatible builds are not part of the public product identity.

---

<p align="center">
  <img src="./assets/x1-tivimate-boundary.svg" alt="X1 TiviMate responsibility boundary" width="100%" />
</p>

## Security / responsibility boundary

X1 TiviMate Community is **control software**.

It does not provide IPTV channels, subscriptions, playlists, portal credentials or copyrighted media. Operators are responsible for the infrastructure, services, credentials, application builds and content they configure, and for ensuring they are authorized to use them.

For production installations:

- use HTTPS;
- use unique administrator credentials;
- enable TOTP where appropriate;
- keep PHP/database packages current;
- protect configuration and runtime storage from direct web access;
- review audit data;
- rotate exposed secrets immediately.

Security reports are welcome. Do not publish live credentials, private keys, customer information or working exploitation details in public issues.

---

## Requirements

Recommended environment:

```text
PHP 8.2+
MariaDB 10.6+ or MySQL 8+
nginx
PDO MySQL
OpenSSL
zlib
mbstring
JSON
HTTPS
```

---

## Installation / Quick Start

Create the environment file:

```bash
cp .env.example .env
```

Configure the installation-specific application URL and database credentials, generate a unique application key, then run:

```bash
php bin/migrate.php
```

Create the first administrator with the included CLI utility and point the web server to the public web root. An example nginx configuration is included in the repository.

### Never expose private runtime paths

Do not serve configuration, storage, internal modules, database tooling or CLI directories directly through the web server.

Generate deployment secrets on the target installation. Never reuse example credentials.

---

## Public distribution

Public packages must not include installation-specific or private material such as:

- environment files with real secrets;
- production database credentials;
- private/signing keys;
- Android keystores or keystore passwords;
- bot/service credentials;
- customer data;
- runtime databases;
- uploaded private application artifacts.

Code protection or obfuscation may make casual copying more difficult, but **obfuscation is not a security boundary**.

---

## Independent project notice

X1 TiviMate Community is an independent X1 community project. It is not presented as an official product of, or as affiliated with, the developers or owners of the TiviMate trademark.

---

## Community distribution

The public project is free to download and use under the distribution terms included with the repository.

Redistribution must preserve the applicable X1 branding and license terms and must not present the software as another vendor's product or include private/commercial X1 components.

See `COMMUNITY_LICENSE.txt` for the repository's distribution terms.

---

## Related X1 systems

- [X1 GitHub](https://github.com/x1-dotcom)
- [X1 Panel XCIPTV](https://github.com/x1-dotcom/X1-Panel-XCIPTV)
- [X1 Smarters V5](https://github.com/x1-dotcom/Smarters-V5)

---

## Community

- Forum — https://forum.x1panel.space
- Discord — https://discord.gg/vSSw6jHmw
- Telegram — https://t.me/+XkuQS_QuD6g4Nzc0

---

<p align="center">
  <strong>PAIR THE DEVICE. CONTROL THE STATE. VERIFY THE RESULT.</strong><br><br>
  <strong>X1 // SOFTWARE · SYSTEMS · OPERATIONS</strong><br><br>
  PUBLIC SOFTWARE. PRIVATE ENGINEERING. ONE X1 IDENTITY.<br><br>
  <strong>© X1Tech Solutions SA · All Rights Reserved</strong>
</p>
