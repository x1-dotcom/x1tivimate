<div align="center">

X1 TiviMate Control

Community Edition

Free community control panel for X1-compatible TiviMate-based APK deployments.

Manage portals, devices, messages, runtime configuration, QR pairing and the X1 Device Agent from a clean web interface.

Forum · Telegram · Discord

</div>

About

X1 TiviMate Control — Community Edition is the free edition of the X1 ecosystem, focused exclusively on compatible TiviMate-based APK deployments.

It is designed to be genuinely useful as a standalone community product — not a crippled demo — while keeping professional fleet, reseller, NOC and automation capabilities in X1 Control Center Commercial.

Community Edition includes

Portal management

Canonical device registry

Device online/offline visibility

Welcome/runtime configuration

Announcements and messages

Basic QR pairing

X1 Device Agent enrollment

Signed Agent heartbeat

Capability reporting

Safe remote actions:

sync_config

show_message

check_update

Audit logging

Secure panel authentication

TOTP two-factor authentication

Local QR generation for 2FA

X1 Community branding and ecosystem links

X1 Device Agent

Phase 2 introduces the X1 Device Agent v2.

The Agent uses one-time enrollment and authenticated device communication:

One-time enrollment
        ↓
Device token
        ↓
HMAC-SHA256 signed requests
        ↓
Heartbeat
        ↓
Capabilities
        ↓
Safe remote commands

The Community Edition intentionally exposes only a conservative command set:

sync_config
show_message
check_update

Advanced fleet actions remain part of X1 Control Center Commercial.

APK compatibility

This release is intended for the supported X1-compatible TiviMate-based APK using package:

ar.tvplayer.tv

Canonical X1 API base:

/api/reseller/tivimate/

A legacy compatibility route is retained for the supplied compatible APK:

/Gizmos_RC11/api/reseller/tivimate/

The legacy route exists only for binary compatibility. The visible product and project identity is X1.

Requirements

Recommended production environment:

PHP 8.2+

MariaDB 10.6+ or MySQL 8+

nginx

PDO MySQL

OpenSSL

zlib

mbstring

JSON

HTTPS

Installation

Clone or upload the Community package to your server.

Create the environment file:

cp .env.example .env

Configure at minimum:

APP_URL=https://your-domain.example
DB_HOST=127.0.0.1
DB_PORT=3306
DB_NAME=x1_tivimate_community
DB_USER=x1_tivimate
DB_PASS=CHANGE_ME

Generate a unique application key:

php -r 'echo base64_encode(random_bytes(32)), PHP_EOL;'

Place the result in:

APP_KEY=

Run the database migrations:

php bin/migrate.php

Create the first administrator:

php bin/create-admin.php \
  --email=admin@example.com \
  --username=admin \
  --password='USE-A-LONG-UNIQUE-PASSWORD'

Point nginx to:

public/

An example configuration is included:

nginx.community.example.conf

Never expose .env, storage/, config/, core/, modules/, database/ or bin/ directly through the web server.

Community vs Commercial

Capability

Community

X1 Control Center

TiviMate control

✅

✅

Portals / runtime / messages

✅

✅

Device registry

✅

✅

Basic Device Agent

✅

✅

Safe remote commands

✅

✅

Advanced Device 360

—

✅

VPN policies

—

✅

Release Vault

—

✅

Staged OTA rollouts

—

✅

Dynamic fleet groups

—

✅

Bulk automation

—

✅

Resellers / customers / licenses

—

✅

Approval workflows

—

✅

NOC / incidents / SLA

—

✅

On-call / runbooks

—

✅

Reliability & production governance

—

✅

Multi-application control

—

✅

The Community Edition is intended for individual/community TiviMate deployments.

X1 Control Center is designed for commercial operations, resellers, large fleets and multi-application environments.

Public distribution

Use the FORUM DIST package for public distribution.

The public build is protected/obfuscated to make casual copying and rebranding more difficult. This protection is not considered a security boundary.

A public package must never contain:

.env

production database credentials

private keys

signing keys

JKS/keystores

keystore passwords

Telegram bot secrets

SaaS credentials

runtime databases

uploaded APK files

customer data

Always generate installation-specific secrets on the target server.

Security

Security reports are welcome.

Please do not publish working exploits, credentials, private keys or customer information in a public issue.

For normal bugs and feature requests, use GitHub Issues or the X1 community channels.

Community

X1 Forum
https://forum.x1panel.space

Telegram
https://t.me/+XkuQS_QuD6g4Nzc0

Discord
https://discord.gg/vSSw6jHmw

Important notice

X1 TiviMate Control is an independent community project and is not presented as an official product of, or as being affiliated with, the developers or owners of the TiviMate trademark.

X1 does not provide IPTV channels, subscriptions, playlists, portal credentials or copyrighted media. The panel is a management/control tool. Users are responsible for ensuring that any services, streams, portals and content they configure are lawful and that they have permission to use them.

License / redistribution

The Community Edition is free to download and use under the included Community Distribution Terms.

You may not:

sell the Community Edition as your own product;

remove X1 branding from redistributed builds without permission;

present the software as another vendor's product;

redistribute private/commercial X1 modules as part of the Community package.

See:

COMMUNITY_LICENSE.txt

for the distribution terms included with the release.

Commercial platform

Need advanced fleet operations?

X1 Control Center adds professional functionality including:

multi-reseller management;

customers and licenses;

advanced Device 360;

VPN policy management;

Release Vault;

staged OTA;

Pilot / Stable release channels;

fleet groups and bulk operations;

approval workflows;

NOC and incident management;

SLA and reliability;

on-call and runbooks;

signed backup/recovery;

production-readiness governance;

multi-app control.

Follow development and announcements through the X1 community channels above.

<div align="center">

X1Tech Solutions SA

Copyright © 2026–Present X1Tech Solutions SA. All Rights Reserved.

Community first. Professional when you need to scale.

</div>
