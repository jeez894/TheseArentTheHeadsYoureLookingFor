# These Aren't the Heads You're Looking For

A somewhat janky character customization expansion for **Star Wars Zero Company**.

The original goal was pretty simple: if all those heads already exist in the game, why shouldn't the player be allowed to use them?

So this mod opens up a much larger part of the game's existing character customization pool, including NPC faces, heads from other species, and — because apparently nobody stopped me — Astromech heads on humanoid characters.

It works. Mostly.

## What it does

- Unlocks a much larger selection of humanoid heads.
- Makes various NPC and named-character heads available to the player.
- Adds heads belonging to several normally restricted species.
- Relaxes some of the game's cross-species customization restrictions.
- Adds a selection of Astromech heads to the humanoid head list.
- Makes Astromech heads work both in the character creator and during gameplay.
- Uses assets already present in the game.

No custom character models or extracted game assets are distributed with the mod.

## A warning before you install it

This is a runtime customization hack, not a perfectly integrated official customization system.

There are rough edges.

Some things can take a second or two to update when changing heads. A previous head may briefly remain visible before disappearing, or a new one may take a moment to appear.

The character customizer in particular likes rebuilding parts of the character while you're using it, so the mod sometimes has to catch up and remount things afterwards.

In other words: if something looks cursed for one second and then fixes itself, that's unfortunately fairly normal.

## Known jank

### Heads can appear or disappear with a delay

Some head changes are not instantaneous.

It can occasionally take around one or two seconds for a head to appear, disappear, or be replaced correctly.

This is especially noticeable when rapidly changing options in the character creator.

### Some heads have forced hair

Certain character models were never designed to be freely combined with the normal player customization system.

As a result, some heads may come with hair or other attached elements that cannot currently be removed through the normal options.

Some combinations will therefore look better than others.

### Missing thumbnails

Not every newly available customization entry has a usable character-creator thumbnail.

Some options may have no thumbnail, an incomplete thumbnail, or otherwise look slightly weird in the selection menu.

The actual head can still work once selected.

### Astromech materials and paint

Astromech head geometry works, but their original material setup doesn't translate perfectly to a humanoid character.

Some paint schemes, tint variants and material details may therefore look different from the original Astromech they came from.

The meshes themselves are mounted independently onto the humanoid skeleton and are positioned correctly in gameplay.

### Character creator weirdness

The character creator can temporarily recreate or replace character components while changing customization options.

Because of that, Astromech heads in particular can occasionally disappear for a moment and then come back once the mod recreates their mount.

Again: clanky, but functional.

## Requirements

- **Star Wars Zero Company**
- **RE-UE4SS / UE4SS**

The mod is currently developed and tested against:

- Unreal Engine 5.6 version of Star Wars Zero Company
- UE4SS v3.0.1 Beta #0
- RE-UE4SS commit `a1e7f571c789f63f3de6773d056be6f778c14dc8`

Other UE4SS versions may work, but haven't been tested by me.

## Installation

### Manual installation

Install UE4SS for Star Wars Zero Company first.

Then extract the mod archive into:

    Star Wars Zero Company\SWZeroCompany\Binaries\Win64\

The final structure should be:

    SWZeroCompany
    └─ Binaries
       └─ Win64
          └─ ue4ss
             └─ Mods
                └─ TheseArentTheHeadsYoureLookingFor
                   ├─ enabled.txt
                   └─ dlls
                      └─ main.dll

The included `enabled.txt` tells UE4SS to load the mod automatically.

**You do not need to edit `mods.txt`.**

Launch the game normally.

### Vortex

The archive also uses the standard UE4SS folder structure and includes `enabled.txt`.

Vortex installation may work with the Star Wars Zero Company Vortex extension, but manual installation remains the known working method.
## Compatibility

The mod changes character customization behaviour at runtime through UE4SS.

Mods that hook or heavily alter the same customization systems may conflict with it.

I haven't attempted to make it universally compatible with every other customization mod.

## Version

Current public version: **0.1.0**

This is the first public release, so expect some rough edges.

## Building from source

The repository contains the source for the UE4SS C++ mod, but does not include RE-UE4SS itself.

A compatible RE-UE4SS checkout must be provided to CMake through `RE_UE4SS_SOURCE_DIR`.

More detailed build instructions will be available in `docs/BUILDING.md`.

## Credits

Created by **Guillaume Rouge / jeez894**.

This project uses **RE-UE4SS** and **PolyHook 2**.

The original C++ mod structure and some of the early hooking work were based on / derived from Sternab's **ZeroCompanyMandoWardrobe** project.

See `LICENSE` and `THIRD_PARTY_NOTICES.md` for the relevant licensing and attribution information.

## Disclaimer

This is an unofficial fan-made mod.

It is not affiliated with or endorsed by the developers or publishers of Star Wars Zero Company, Lucasfilm, Disney, or any of their respective partners.

No copyrighted game assets are distributed with this repository.
