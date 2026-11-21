# ✻ dwb-bridge

![Platform](https://img.shields.io/badge/platform-macOS%20·%20Linux%20·%20Raspberry%20Pi%20·%20OpenWrt-2ea44f) ![Site](https://img.shields.io/website?url=https%3A%2F%2Fgetdwb.com&label=getdwb.com) ![License](https://img.shields.io/badge/license-proprietary-8b949e)

**Let cloud coding agents (Claude Code, Codex, ChatGPT) work on your own machines.**

A ~10 MB static binary (`dwb-host`) runs on each of your machines — desktop, servers, Raspberry Pi, even OpenWrt routers — makes an outbound-only connection, and executes the commands a cloud agent sends. Every command is visible in your terminal and a web console where you approve plans and read diffs.

- 🌐 Site: https://getdwb.com/
- 📖 Case posts: https://getdwb.com/blog/
- 💿 Download: https://getdwb.com/download/

## Why

- **Local agents are heavy** — a single idle claude process holds ~127 MB; four sessions grind a machine. dwb-bridge keeps the reasoning in the cloud: one dwb-host carries all sessions (~15 MB measured), and overall machine load dropped by **more than 30%** with several running at once.
- **Agents can't reach your materials** — projects, intranet systems, NAS and connected devices live on your machines. dwb-bridge brings the agent to them over an outbound-only connection: no public IP, no open ports, no VPN.
- **Credentials don't sprawl** — the AI account is logged in at exactly one place (the cloud environment); every machine holds only a resettable key. On connect it also shares your local CLAUDE.md/AGENTS.md and installed skills so the agent follows your setup.

## Install

```sh
brew tap vesofts/tap
brew trust vesofts/tap
brew install --cask vesofts/tap/dwb-desktop
```

or on any Linux machine / Raspberry Pi / router:

```sh
curl -fsSL https://getdwb.com/install.sh | sh
```

## Supported devices

| Device | Architectures | Install |
|---|---|---|
| MacBook / iMac | Apple Silicon · Intel | dmg · Homebrew |
| Linux servers | x86_64 · arm64 | script · tar.gz |
| Raspberry Pi | arm64 · armv6l | script |
| OpenWrt routers | aarch64 · mipsle | script |
| NAS | x86_64 · arm64 | script · tar.gz |
| Android | APK | direct download |
| iPhone / iPad | PWA | add to home screen |

## Case posts

- [Local agents stutter when you open more? Cut load by over 30%](https://getdwb.com/blog/multi-session-load/)
- [One cloud agent for every computer you own](https://getdwb.com/blog/multi-device-fleet/)
- [AI agents on Raspberry Pi, OpenWrt routers and handhelds](https://getdwb.com/blog/lightweight-devices/)
- [Get an agent working on a new machine in 3 minutes](https://getdwb.com/blog/new-machine-no-local-agent/)

Honest notes: closed source (the security model is documented — outbound-only, reviewable join scripts, resettable keys); command output transits the relay; task-side CPU still runs on your machine.
