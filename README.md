# TEON

**Traid's EON Nexus** is a Windows launcher for Pokémon Emerald runs. Make a profile, choose the generations you want, save a randomization, and play with or without NameLocke. Profiles keep their games, settings, and saves separate.

**Current status:** Windows x64 preview. [Get the latest build from Releases](../../releases). Download the file named `TEON-<version>-win-x64.zip`, then extract the whole ZIP. GitHub's automatic **Source code** downloads contain only this release repository's documentation, not the launcher.

## Before you start

| You need | Why |
| --- | --- |
| Windows x64 | The current launcher build targets Windows. |
| Your own clean Pokémon Emerald (U), revision 0 ROM | TEON verifies the original 16 MiB game before preparing an expanded run. A randomized or modified ROM will not work as the base game. |
| [mGBA for Windows](https://mgba.io/downloads.html) | TEON opens your game in mGBA. Select its executable in TEON's Settings. |
| Java 11 or newer | The expanded randomizer runs on Java. Install a Java runtime such as [Eclipse Temurin](https://adoptium.net/temurin/releases) and make sure `java -version` works in PowerShell. |
| Internet access on first use | TEON downloads and verifies its pinned randomizer components. NameLocke downloads its speech model when you first start a voice session. |
| A microphone, if using NameLocke | Voice matching listens to the party in your current game. |

The release includes .NET and the small Python runtime it needs. You do not need Visual Studio, WSL, or a build toolchain to play.

## Set up a run

1. Extract the release ZIP to a folder you can keep, then run `TEON.exe`.
2. Open **Settings** and choose your mGBA executable. Open **Game Setup** and select your clean Emerald ROM. These are separate files: the emulator runs games; the ROM supplies the base game.
3. Open **Pokémon Emerald**, create a profile, and choose which Pokémon generations to include.
4. In the profile's **Mods** tab, install **Expanded Randomizer**. Install **NameLocke** too if you want the voice challenge.
5. Open the **Randomizer** tab and choose **Configure Randomizer**. Choose the options you want in the randomizer window, select **Randomize (Save)**, and close that window. New profiles start without randomization options enabled.
6. Return to the profile and use its play button. TEON checks the saved randomization and prepares the game. A NameLocke profile opens its own control window before launching mGBA.

Your clean ROM is kept as the input. TEON writes playable games and saves under your Windows user data directory, not into this release repository.

## Supported games and mods

<details>
<summary><strong>Pokémon Emerald</strong> - expanded engine, Gen I-IX pool</summary>

TEON accepts a clean Emerald (U), revision 0 ROM and prepares an expanded game for the generations selected in your profile. This is the only supported game at present. A generation selection restricts the Pokémon pool; it does not change which base ROM you provide.

### Available mods

<details>
<summary><strong>Expanded Randomizer</strong> - configure a new run</summary>

Choose what to randomize in the full randomizer window. TEON applies your profile's generation selection automatically and verifies the saved result before using it. You must select **Randomize (Save)** in that window to create a game. The randomizer interface is based on KittyPBoxx's UPR-Speedchoice work and the Universal Pokémon Randomizer lineage; credit belongs to their contributors.

After you save a run, **Re-Randomize** can create another with the last saved settings. It asks before replacing the previous run and deleting its game and saves. Copy anything you want to keep before confirming.

</details>

<details>
<summary><strong>NameLocke</strong> - voice challenge</summary>

**Developed by Traid. Original idea by ReadyJP.** NameLocke listens for the species or nickname of a Pokémon in your current party and sends a faint request for that individual Pokémon. A Pokémon in the PC is outside the voice matching party. During battle, a requested faint may wait for a safe point in the game.

To play, install Expanded Randomizer and NameLocke in the same profile, create a randomization, then open the profile's game. In the NameLocke window:

1. Choose **Open game** to launch mGBA.
2. In mGBA 0.10.x, select **Tools > Scripting... > File > Load Script...**. Use **Lua script** in the NameLocke window for the correct folder and filename. Load the script again whenever mGBA starts.
3. Choose your microphone and select **Start session**. The session can wait for the script if you start it first.
4. Turn on **Enable live kill** if you want matched names to faint Pokémon. With it off, matching runs in dry-run mode.

The **Lua script** button points to the correct script for the profile you launched. Leave the script beside `game.gba` in place: TEON checks it against that specific game when building and playing.

</details>

</details>

## Frequently asked questions

<details>
<summary>Which file do I download from GitHub?</summary>

Open **Releases** and download `TEON-<version>-win-x64.zip` under Assets. Extract it, then launch `TEON.exe`. The automatic **Source code (zip)** and **Source code (tar.gz)** links are GitHub snapshots of this documentation repository and cannot run the launcher.

</details>

<details>
<summary>Why do I need Java if TEON comes as an EXE?</summary>

The launcher includes its .NET runtime, but its expanded randomizer is a separate Java program. Install Java 11 or newer, open PowerShell, and run `java -version`. TEON downloads the pinned randomizer files when they are needed; the first download requires internet access.

</details>

<details>
<summary>Where do I choose mGBA and where do I choose the Emerald ROM?</summary>

Choose the mGBA `.exe` in TEON **Settings**. Choose your clean Emerald `.gba` in **Game Setup**. mGBA is the emulator; Emerald is the input game. The release contains neither of them.

</details>

<details>
<summary>Why does NameLocke show two Lua files?</summary>

The build keeps `game.namelock.lua` beside its matching `game.gba` so TEON can verify that pair. When you launch, TEON copies that script to a stable `namelock.lua` path for the profile. Use the path shown by the **Lua script** button in the NameLocke window. It is refreshed when you launch that profile's game.

</details>

<details>
<summary>Where are my saves? Does Re-Randomize keep them?</summary>

Use the profile's **Saves** tab to see its save files and open their folders. A NameLocke game's battery save is `game.sav` beside `game.gba` in TEON's local user data. Re-Randomize asks before it deletes the previous run's game and saves. Back up a save outside that run before you confirm if you want to keep it.

</details>

<details>
<summary>Why did NameLocke hear a name but nothing fainted?</summary>

Check that **Enable live kill** is on, mGBA has the matching Lua script loaded, and the session says it is listening. A battle faint may wait for a safe point. If the game is stuck or a queued faint never finishes, report the steps, the last NameLocke log lines, and the version from `release-manifest.json`. Do not upload your ROM or save file to a public issue.

</details>

<details>
<summary>Can I add a different game or another mod?</summary>

The current release supports Pokémon Emerald with Expanded Randomizer and NameLocke. Other games and mods are not supported by this build.

</details>

## Support and credits

When reporting a problem, include the TEON version, Windows version, mGBA version, what you clicked, and the exact error text. Keep ROMs, saves, personal file paths, and private keys out of public issues. For a suspected security issue, see [SECURITY.md](SECURITY.md).

TEON and NameLocke development: **Traid**. NameLocke's original idea: **ReadyJP**. Expanded randomizer and game engine work is credited to its upstream creators in [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md). Those projects retain their own licenses.

Official compiled TEON releases may be used under the terms in [LICENSE](LICENSE). TEON is not affiliated with Nintendo, The Pokémon Company, or Game Freak. No Pokémon ROM is included.
