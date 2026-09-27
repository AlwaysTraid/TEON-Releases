# TEON

**Traid's EON Nexus** is a Windows launcher for randomized Pokémon Emerald runs and NameLocke. Keep each run's generations, mods, game, and saves in its own profile.

[Download a release](../../releases) · [Set up a run](#get-started) · [Games and mods](#games-and-mods) · [FAQ](#faq)

> **Windows x64 preview.** Download `TEON-<version>-win-x64.zip` from **Releases > Assets**. GitHub's automatic Source code ZIP is just this documentation repository.

## Get started

1. Extract the release ZIP and run `TEON.exe`.
2. In **Settings**, select [mGBA](https://mgba.io/downloads.html). In **Game Setup**, select your own clean **Pokémon Emerald (U), revision 0** ROM.
3. Create a profile, choose your generations, and install **Expanded Randomizer**. Add **NameLocke** if you want voice-based fainting.
4. Open **Randomizer**, choose your options, then click **Randomize (Save)** in its window.
5. Return to the profile and select its play button. For NameLocke, follow the short [voice setup](#games-and-mods) below.

**Also required:** [Java 11 or newer](https://adoptium.net/temurin/releases) for the randomizer (`java -version` should work), internet access for first-time downloads, and a microphone for NameLocke. The release already includes .NET and its Python runtime. You do not need WSL or build tools.

## Games and mods

<details>
<summary><strong>Pokémon Emerald</strong> · Expanded engine · Gen I-IX</summary>

Use a clean 16 MiB Emerald (U), revision 0 ROM. TEON creates the expanded game from a copy and uses the generations selected for your profile.

**Available mods**

<details>
<summary><strong>Expanded Randomizer</strong> · Build a different run</summary>

- Choose your settings in the randomizer window; click **Randomize (Save)** to create the game.
- **Re-Randomize** reuses the saved settings. It asks before deleting the previous run and saves.
- Randomizer interface by KittyPBoxx, based on UPR-Speedchoice and Universal Pokémon Randomizer work.

</details>

<details>
<summary><strong>NameLocke</strong> · Voice challenge</summary>

**Developed by Traid. Original idea by ReadyJP.**

- Say the species or nickname of a Pokémon in your current party to request its faint.
- From your profile, open NameLocke and click **Open game**.
- In mGBA 0.10.x, go to **Tools > Scripting... > File > Load Script...**. The **Lua script** button in NameLocke shows the correct folder and filename. Load it once per mGBA launch.
- Select your microphone and click **Start session**. Turn on **Enable live kill** to make matches affect the game; otherwise matching runs as a dry run.

</details>

</details>

## FAQ

<details>
<summary>Which download do I need?</summary>

Choose `TEON-<version>-win-x64.zip` under **Releases > Assets**. Extract the whole ZIP before running `TEON.exe`. The automatic Source code ZIP cannot launch TEON.

</details>

<details>
<summary>Why does the randomizer ask for Java?</summary>

TEON includes its .NET runtime, but the expanded randomizer runs on Java. Install Java 11 or newer and check `java -version` in PowerShell.

</details>

<details>
<summary>Where are my saves?</summary>

Open the profile's **Saves** tab. Use its folder action to find a save. **Re-Randomize** asks before replacing the previous run, including its saves.

</details>

<details>
<summary>NameLocke heard a name. Why did nothing faint?</summary>

Check **Enable live kill**, the selected microphone, and whether you loaded the matching Lua script in mGBA. During battle, a faint can wait for a safe game state. If it stays stuck, include the last NameLocke log lines in a bug report.

</details>

<details>
<summary>Can I use another game or mod?</summary>

This preview supports Pokémon Emerald with Expanded Randomizer and NameLocke.

</details>

## Credits and support

TEON and NameLocke were developed by **Traid**. **ReadyJP** came up with the original NameLocke idea. The expanded engine, randomizer, emulator, and other third-party projects retain their own credits and terms in [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).

For a bug report, include your TEON version, Windows version, mGBA version, steps to reproduce, and the exact error. Do not upload ROMs, saves, personal paths, or private keys to a public issue. See [SECURITY.md](SECURITY.md) for sensitive reports.

TEON does not include a Pokémon ROM and is not affiliated with Nintendo, The Pokémon Company, or Game Freak. Official builds are distributed under [LICENSE](LICENSE).
