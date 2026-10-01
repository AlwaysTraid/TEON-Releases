# TEON

### A home for every Emerald run.

Randomize Pokémon Emerald, choose the generations you want, and keep each run in its own profile. Add NameLocke when you want your voice to decide who faints.

**Windows x64 preview** &nbsp; · &nbsp; [Download](../../releases) &nbsp; · &nbsp; [Set up](#get-playing) &nbsp; · &nbsp; [Games and mods](#games-and-mods) &nbsp; · &nbsp; [Soul Link](#soul-link)

> [!IMPORTANT]
> Download **`TEON-<version>-win-x64.zip`** under **Releases > Assets**. A private friend-test package may instead be named **`TEON-Streamer-win-x64.zip`**. Extract it before opening `TEON.exe`. GitHub's automatic **Source code** download contains documentation only.

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

### NameLocke commands

Type these in **mGBA > Tools > Scripting...**, not in the OBS browser console. Run `namelock.help()` to list the commands supported by the loaded script. Party slots are numbered **1–6**.

| Command | What it does |
| :-- | :-- |
| `namelock.help()` | List the loaded script's commands. |
| `namelock.party()` | Show validated party slots, names, HP and individual IDs. |
| `namelock.battle()` | Show the current battle information. |
| `namelock.bridge()` | Check the connection to the NameLocke companion. |
| `namelock.hookstatus()` | Show the game hook's diagnostic status. |
| `namelock.queue()` | Show pending battle faint requests. |
| `namelock.kill(1)` | Faint the Pokémon currently in party slot 1; outside battle only. |
| `namelock.killpid(0x12345678)` | Faint the individual with this PID; replace the example with its ID from `party()`. |
| `namelock.killpids({0x12345678, 0x87654321})` | Request a batch of faints for the listed PIDs. |
| `namelock.killbattle(1)` | During battle, target slot 1 from the stable pre-battle party order. |

These manual faint commands set HP to zero; they do not release Pokémon. During Soul Link, a verified faint also affects the linked partner. **Solo NameLocke has no new reset/heal command in this build.** The shared encounter reset is documented below.

**Developed by Traid. Original idea by ReadyJP.**

</details>

<br>

<a id="soul-link"></a>
<details>
<summary><strong>03 &nbsp; Soul Link</strong> &nbsp; | &nbsp; Two trainers. Linked encounters.</summary>

<br>

Soul Link uses **Connect With Partner** in the TEON launcher. Room hosting and joining use the bundled **Epic Online Services (EOS)** connection. Players do not need an Epic account sign-in, SDK installation, server address, separate relay application, or port forwarding. Internet access is required.

### Connect and start playing

1. Both players extract the same complete build on their own Windows PCs and open `TEON.exe` normally. Each player enters their own name at the top right.
2. The host opens **Connect With Partner**, chooses **Create room**, and shares the room code privately.
3. The other player enters the code and selects **Request to join**. The host checks the displayed name and accepts the request.
4. Confirm **Connected** in both launchers. Use **Check connection** and confirm acknowledgement before starting the games.
5. Each player opens their own NameLocke profile through **Build + Play / Play**, then loads that game's Lua script in mGBA. After updating TEON, launch through the profile again and reload the updated script.
6. Check **Bridge · connected**, the partner's name, and the **Soul Link** tab in each NameLocke window. The TEON connection enables Soul Link automatically; there is no separate Start Soul Link button.
7. Start microphone sessions when ready. Begin with **Live Kill off** to check matching, then enable it to apply voice kills. Encounter detection does not require the microphone to be running.

Keep the host's TEON application open. Quitting the host ends the room; create and share a new code next time. A new room does not erase the saved run history. Closing a launcher to its system tray can leave it running; use **Quit** to exit fully.

EOS identifies a Windows user/device, so two copies under the same Windows account are not the internet test setup. Use two PCs for a friend connection. The developer's local two-player runner uses a separate local test transport.

### Encounters, eliminations and OBS

- Starters pair with starters. After each player receives the initial Pokédex and Poké Balls, the first eligible wild encounter in each location records a catch or failure automatically. Earlier grass battles do not spend the location, and players can have different numbers of those battles.
- Encounters pair by location and Pokémon identity, not by party slot. Later wild encounters in an already-used location do not replace its result. Catches sent to the PC are included.
- A failed encounter invalidates the pair. A natural faint or a live voice match eliminates both linked members; a partner's later first catch in that location inherits an existing elimination. Pokémon are fainted, never released.
- Each microphone can match a species or nickname from either current party. **Live Kill off** is a dry run and must not change HP.
- Open **OBS overlay** in NameLocke and use its displayed URL as an OBS Browser Source. The paired view keeps linked Pokémon side by side, shows their location and elimination marker, and queues notifications at the top. It displays at most six pair rows per page and cycles pages if necessary. A dead pair remains visible while either linked member is still in a party.

### Soul Link commands

Type these in **either player's mGBA scripting console**. Only one player needs to request a reset. Both games must use the updated scripts, remain connected, and be running outside battle for the reset to finish.

| Command | What it does |
| :-- | :-- |
| `namelock.seteliminated("Route 101", false)` | Reset Route 101's elimination on both games. Use the location shown in the Soul Link tab. |
| `namelock.seteliminated("Starter", false)` | Reset the starter pair on both games. |
| `namelocke.seteliminated("Route 101", false)` | Accepted alias for the same shared reset in mGBA. |

Wait for **Encounter reset · both games ready** before continuing. Caught party members regain full HP and lose status conditions; PP is unchanged. Their identities and pairing stay intact. A boxed member's elimination is cleared, and Emerald restores its HP normally on withdrawal. A failed side gets another eligible encounter attempt, while its caught counterpart remains paired. Other locations are unaffected, and normal voice/natural-faint rules apply again afterward. Save both games when the reset completes.

A reset is **not a save-history rewind**. Loading an older save can pause detection with a rollback message because recorded encounters are newer than that save. Resume the matching saves instead of repeatedly requesting an elimination reset. The console reports a refusal if a paused or mismatched run prevents the request.

**OBS-only marker control:** In the overlay's browser developer console, `namelocke.seteliminated("Route 101", false)` only hides that page's red marker; passing `true` restores the actual marker display. It does not heal Pokémon or alter shared history. Use the **mGBA console** for the gameplay reset above.

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

This preview supports Pokémon Emerald, Expanded Randomizer, NameLocke, and the Soul Link partner mode described above.

</details>

---

## Made by Traid

**TEON and NameLocke:** Traid &nbsp; · &nbsp; **NameLocke concept:** ReadyJP

The OBS party icon sheet comes from [Pokémon Showdown / Smogon](https://github.com/smogon/sprites). Pokémon Showdown and the original artists retain their respective rights. Other credits and terms are in [Third-party notices](THIRD_PARTY_NOTICES.md).

[Report a bug](../../issues) &nbsp; · &nbsp; [Security](SECURITY.md) &nbsp; · &nbsp; [License](LICENSE)

<sub>TEON does not include a Pokémon ROM and is not affiliated with Nintendo, The Pokémon Company, Game Freak, or Pokémon Showdown.</sub>
