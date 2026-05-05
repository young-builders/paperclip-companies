---
name: roblox-setup
description: Initialize a new Roblox game project — Rojo config, folder structure, Selene linting, GitHub repo, default.project.json, base modules
---

Set up a new Roblox game project from scratch. Steps: create Rojo project (`default.project.json`), create src/ folder structure, configure Selene (`.selene.toml`), set up Luau LSP config, create base modules, initialize GitHub repo with CI workflow.

## default.project.json (always use this template)

```json
{
  "name": "GAME_NAME",
  "tree": {
    "$className": "DataModel",
    "ServerScriptService": {
      "$className": "ServerScriptService",
      "$path": "src/ServerScriptService"
    },
    "ReplicatedStorage": {
      "$className": "ReplicatedStorage",
      "$path": "src/ReplicatedStorage"
    },
    "StarterPlayer": {
      "$className": "StarterPlayer",
      "StarterPlayerScripts": {
        "$className": "StarterPlayerScripts",
        "$path": "src/StarterPlayerScripts"
      },
      "StarterCharacterScripts": {
        "$className": "StarterCharacterScripts",
        "$path": "src/StarterCharacterScripts"
      }
    },
    "StarterGui": {
      "$className": "StarterGui",
      "$path": "src/StarterGui"
    },
    "Workspace": {
      "$className": "Workspace",
      "FilteringEnabled": true
    }
  }
}
```

## src/ Folder Structure

```
src/
  ServerScriptService/
    GameController.server.lua   ← core game loop
    DataManager.server.lua      ← DataStore wrapper
  ReplicatedStorage/
    Remotes/                    ← all RemoteEvents + RemoteFunctions (network-programmer owns)
    Shared/
      Config.lua                ← game config (asset IDs, settings)
      AssetConfig.lua           ← ALL asset IDs here only (asset-specialist owns)
      Types.lua                 ← shared type definitions (data-architect owns)
  StarterPlayerScripts/
    InputHandler.client.lua
  StarterCharacterScripts/
    CharacterSetup.client.lua
  StarterGui/
    MainGui/                    ← UI components (ui-programmer owns)
```

## .selene.toml

```toml
std = "roblox"
```

## GitHub Actions CI (`.github/workflows/ci.yml` in young-builders/games)

```yaml
name: CI
on: [push, pull_request]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Install Rojo
        run: curl -fsSL https://github.com/rojo-rbx/rojo/releases/latest/download/rojo-linux.zip -o rojo.zip && unzip rojo.zip && chmod +x rojo && sudo mv rojo /usr/local/bin/
      - name: Build
        run: rojo build default.project.json --output game.rbxl
      - name: Lint (Selene)
        run: selene src/ || true
```
