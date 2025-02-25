[github release]: https://github.com/yorqat/tyconia/releases
[XDG Base Directory]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html

# Introduction

![Tyconia hero text](./title_0.png  "Optional title")

First of all, thank you for finding a niche use for tyconia.

Tyconia is a game engine built on top of bevy to build isometric 2.5D automation and logistics games. It relies on mostly declarative programming through a configuration pattern with ron.

## Installation
You may install tyconia from the following official release channels:

|         **Vendor** | **Page** |
|------------|----------|
| **Steam**  | <img height="120px" src="https://i.kym-cdn.com/entries/icons/mobile/000/032/606/cover2.jpg" /> |
| **Epic games**  | <img height="120px" src="https://i.kym-cdn.com/entries/icons/mobile/000/032/606/cover2.jpg" /> |
| **Itch.io**  | <img height="120px" src="https://i.kym-cdn.com/entries/icons/mobile/000/032/606/cover2.jpg" /> |


Or download directory from a [github release].


## Config Directory
When you're developing a mod, it should be at your respective config folder.

| **Platform**      | **Config Folder Location**                                  | **Notes**                                           |
|-------------------|------------------------------------------------------------|-----------------------------------------------------|
| **Windows**       | `%APPDATA%\tyconia\mods\<your_mod>`                         | Use `%LOCALAPPDATA%` for non-roaming configs.       |
| **macOS**         | `~/Library/Application Support/tyconia/mods/<your_mod>`     | `~/Library/Preferences/` for `.plist` files.        |
| **Linux**         | `~/.config/tyconia/mods/<your_mod>`                         | Follows the [XDG Base Directory] spec. |
| **Steam (Proton)** | `~/.steam/steam/steamapps/compatdata/<AppID>/pfx/drive_c/users/steamuser/AppData/Roaming/tyconia/mods/<your_mod>` | Replace `<AppID>` with the game's Steam AppID.      |
| **Flatpak (Linux)**| `~/.var/app/<AppID>/config/tyconia/mods/<your_mod>`        | Replace `<AppID>` with the Flatpak app ID.          |
| **Snap (Linux)**   | `~/snap/tyconia/current/mods/<your_mod>`                   | Snap apps store configs in versioned directories.   |

## File structure
A mod will have this structure

     mod_name/ # no matter what the directory name is as all info will be from meta.ron
    │
    ├── meta.ron         # Metadata: name, version, author, dependencies, description
    │
    ├── assets/
    │   ├── textures/        # Sprites, UI elements
    │   ├── sounds/          # SFX and music
    │   └── fonts/           # Custom fonts if needed
    │
    ├── definitions/         # Core data definitions
    │   ├── items.ron        # All items introduced/modified
    │   ├── recipes.ron      # Crafting or cooking recipes
    │   ├── research.ron     # Research tree additions
    │   ├── entities.ron     # Machines, NPCs, or interactive objects
    │   └── levels.ron       # Level layouts, if applicable
    │
    ├── story/               # Story beats, dialogue, and narrative
    │   └── beats.ron        # Narrative elements, dialogue, etc.
    │
    ├── scenarios/           # Custom gameplay style
    │   ├── sushi_restaurant.ron  
    │   └── lemon_stand.ron  
    │
    ├── ui/                   # Custom configurations
    │   └── menus.ron        # Custom menus, buttons, etc.
    │
    └── scripts/              # Custom scripting
        └── example.rhai      # Example mod logic (or leave empty if RON-only)

## How it works
