# TEON

### A home for every Emerald run.

Randomize Pokémon Emerald, choose the generations you want, and keep each run in its own profile. Add NameLocke when you want your voice to decide who faints.

**Windows x64 preview** &nbsp; · &nbsp; [Download](../../releases) &nbsp; · &nbsp; [Set up](#get-playing) &nbsp; · &nbsp; [Games and mods](#games-and-mods)

> [!IMPORTANT]
> Download **`TEON-<version>-win-x64.zip`** under **Releases > Assets**. Extract it before opening `TEON.exe`. GitHub's automatic **Source code** download contains documentation only.

---

## Get playing

| Step | What to do |
| :-- | :-- |
| **01 / OPEN** | Extract the ZIP, then open `TEON.exe`. |
| **02 / CONNECT** | Set [mGBA](https://mgba.io/downloads.html) in **Settings**. Add your own clean **Pokémon Emerald (U), revision 0** ROM in **Game Setup**. |
| **03 / CREATE** | Make a profile and select your generations. Add **Expanded Randomizer** and, if you want the voice challenge, **NameLocke**. |
| **04 / PLAY** | Choose your randomizer options, click **Randomize (Save)** in its window, then return to your profile and press **Play**. |

<sub>Also needed: <a href="https://adoptium.net/temurin/releases">Java 11+</a> for the randomizer, internet on first setup, and a microphone for NameLocke. The ZIP includes .NET and its Python runtime. No WSL or build tools needed.</sub>

---

## Games and mods

<details open>
<summary><strong>◇ Pokémon Emerald</strong> &nbsp; | &nbsp; Expanded engine &nbsp; | &nbsp; Generations I-IX</summary>

<br>

Bring your own clean **16 MiB Emerald (U), revision 0** ROM. TEON expands a copy for your profile; your original stays where you put it.

### Choose your mods

<details>
<summary><strong>01 &nbsp; Expanded Randomizer</strong> &nbsp; | &nbsp; A new run every time</summary>

<br>

Pick your own settings in the randomizer window and click **Randomize (Save)**. **Re-Randomize** uses those settings again and asks before replacing the current run and saves.

**Randomizer credit:** KittyPBoxx, building on UPR-Speedchoice and Universal Pokémon Randomizer.

</details>

<br>

<details>
<summary><strong>02 &nbsp; NameLocke</strong> &nbsp; | &nbsp; Say a name. Risk a faint.</summary>

<br>

Speak a current party member's **species or nickname**. When live kills are enabled, NameLocke sends a faint request to the game.

1. Open **NameLocke** from your profile and select **Open game**.
2. In mGBA 0.10.x, open **Tools > Scripting... > File > Load Script...**. Use NameLocke's **Lua script** button to find the right script. Load it once each time you launch mGBA.
3. Select your microphone, start the session, and switch on **Enable live kill**.

**Developed by Traid. Original idea by ReadyJP.**

</details>

<br>

</details>

---

## Good to know

<details>
<summary><strong>Where are my saves?</strong></summary>

Open your profile's **Saves** tab. Re-Randomize asks before removing the old run and its saves.

</details>

<details>
<summary><strong>Why does NameLocke hear a name without a faint?</strong></summary>

Check **Enable live kill**, your microphone, and the script loaded in mGBA. During battle, a faint may wait for a safe moment. If it stays stuck, include the last NameLocke log lines in a bug report.

</details>

<details>
<summary><strong>Can I play a different game?</strong></summary>

This preview supports Pokémon Emerald with the two mods shown above.

</details>

---

## Made by Traid

**TEON and NameLocke:** Traid &nbsp; · &nbsp; **NameLocke concept:** ReadyJP

The OBS party icon sheet comes from [Pokémon Showdown / Smogon](https://github.com/smogon/sprites). Pokémon Showdown and the original artists retain their respective rights. Other credits and terms are in [Third-party notices](THIRD_PARTY_NOTICES.md).

[Report a bug](../../issues) &nbsp; · &nbsp; [Security](SECURITY.md) &nbsp; · &nbsp; [License](LICENSE)

<sub>TEON does not include a Pokémon ROM and is not affiliated with Nintendo, The Pokémon Company, Game Freak, or Pokémon Showdown.</sub>
