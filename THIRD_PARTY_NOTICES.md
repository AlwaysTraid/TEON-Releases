# TEON third-party notices

TEON original code is Copyright (c) 2026 Traid. TEON's license does not relicense
third-party software. Each third-party component remains subject to its own upstream
license and copyright terms.

TEON does **not** distribute a Pokemon Emerald ROM, save file, emulator state, or the
upstream Emerald EX / Speedchoice developer ELF, MAP, C header, source tree, or Arm GNU
toolchain in its public release package.

## Components present in the Windows release

### Microsoft .NET 8

TEON is published as a self-contained .NET 8 Windows application. Microsoft .NET is
licensed under its applicable Microsoft and open-source component terms.

Source / notices: https://github.com/dotnet/runtime

### Whisper.net / Whisper.net.Runtime 1.9.1

Whisper.net is used for speech transcription. The project identifies its license as
MIT. TEON ships only the Windows x64 native runtime files required by the launcher.
Whisper.net incorporates whisper.cpp as documented by its upstream project.

Project: https://github.com/sandrohanea/whisper.net
License: https://github.com/sandrohanea/whisper.net/blob/main/LICENSE

### NAudio 2.4.0

NAudio is used for Windows microphone/audio integration. NAudio 2.x is licensed under
the MIT License.

Project: https://github.com/naudio/NAudio
License: https://github.com/naudio/NAudio/blob/master/LICENSE

### Pokémon Showdown party icon sheet

The NameLocke OBS overlay includes `pokemonicons-sheet.png`, sourced from
Pokémon Showdown / Smogon's sprite resources:
https://play.pokemonshowdown.com/sprites/pokemonicons-sheet.png

Sprite project and rights information: https://github.com/smogon/sprites

The Smogon sprite repository's MIT license applies to repository code, not to
its Pokémon artwork. Its maintainers state that Pokémon sprite rights belong
to Nintendo, Game Freak, and The Pokémon Company, and that use of some
community-created sprites should be discussed with the maintainers first.
Attribution here does not grant permission to redistribute artwork. TEON is
not affiliated with Pokémon Showdown or Smogon.

### Pokémon-style overlay font

The NameLocke OBS overlay includes a Game Boy-style font attributed by the
project's asset inventory to PascalPixel's `pokemon-font`.

Project: https://github.com/PascalPixel/pokemon-font
The font remains subject to its creator's terms; the TEON license does not
cover the font artwork.

### CMU Pronouncing Dictionary (CMUdict)

NameLocke embeds a compressed copy of CMUdict to convert ordinary English words
into ARPAbet phonemes locally. It is used only for pronunciation matching; no
network service or user-side pronunciation package is required.

Project: https://github.com/cmusphinx/cmudict

License notice:

```text
Copyright (C) 1993-2015 Carnegie Mellon University. All rights reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions
are met:

1. Redistributions of source code must retain the above copyright
   notice, this list of conditions and the following disclaimer.
   The contents of this file are deemed to be source code.

2. Redistributions in binary form must reproduce the above copyright
   notice, this list of conditions and the following disclaimer in
   the documentation and/or other materials provided with the
   distribution.

This work was supported in part by funding from the Defense Advanced
Research Projects Agency, the Office of Naval Research and the National
Science Foundation of the United States of America, and by member
companies of the Carnegie Mellon Sphinx Speech Consortium. We acknowledge
the contributions of many volunteers to the expansion and improvement of
this dictionary.

THIS SOFTWARE IS PROVIDED BY CARNEGIE MELLON UNIVERSITY ``AS IS'' AND
ANY EXPRESSED OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO,
THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR
PURPOSE ARE DISCLAIMED.  IN NO EVENT SHALL CARNEGIE MELLON UNIVERSITY
NOR ITS EMPLOYEES BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT
LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE,
DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY
THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
(INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
```

### CPython 3.12.10 embeddable distribution

TEON's sealed NameLocke runtime pack contains the official Windows x64 CPython
embeddable runtime. The complete Python `LICENSE.txt` supplied by Python.org remains
inside that runtime pack beside the Python binaries.

Project: https://www.python.org/
License information: https://docs.python.org/3.12/license.html

## Projects used by TEON but not redistributed as developer artifacts

### Emerald EX / Speedchoice / Gen 9 engine lineage

TEON credits KittyPBoxx, ROM Hacking Hideout (RHH), pret/pokeemerald contributors,
and the pokeemerald-expansion contributor community for the expanded Emerald engine
work that TEON targets.

The public TEON release intentionally does **not** redistribute the pinned engine ELF,
MAP, `species.h`, engine source tree, or a compiled Pokemon ROM. The release contains
only TEON-generated runtime metadata (addresses, hashes, species-name metadata and
layout proofs) plus TEON's NameLocke payload. This avoids treating public repository
availability or requested credit as a grant to redistribute upstream build artifacts.

Relevant upstream projects:
- https://github.com/KittyPBoxx/pokeemerald-ex-speedchoice-maprando-gen9
- https://github.com/rh-hideout/pokeemerald-expansion
- https://github.com/pret/pokeemerald

RHH specifically asks projects using pokeemerald-expansion to credit RHH; TEON does so
here and in its public documentation.

### Universal Pokemon Randomizer / UPR-ZX / Speedchoice Gen 9

TEON's randomizer workflow is based on the Universal Pokemon Randomizer lineage. The
UPR-ZX codebase is GPL-3.0 licensed. The compact TEON release does not hide or relicense
GPL-covered UPR code as TEON proprietary code. Where TEON obtains or runs a pinned UPR
component, it keeps that component's identity and license separate from TEON.

Projects:
- https://github.com/Ajarmar/universal-pokemon-randomizer-zx
- https://github.com/Dabomstew/universal-pokemon-randomizer

### mGBA

TEON supports mGBA for game execution. mGBA is Copyright (c) 2013-2026 Jeffrey Pfau
and contributors and is distributed upstream under the Mozilla Public License 2.0.

Project: https://github.com/mgba-emu/mgba
License: https://github.com/mgba-emu/mgba/blob/master/LICENSE

## Release-build-only tooling

The TEON release process uses GNU Arm binutils on the developer/release machine to
pre-link the frozen NameLocke payload. Those Arm/GNU executables are **not present in
the public TEON ZIP or sealed runtime pack**.

## Pokemon / Nintendo content

Pokemon, Pokemon Emerald, and related trademarks and game content belong to their
respective owners. TEON is not affiliated with Nintendo, The Pokemon Company, or Game
Freak. Users provide their own legally obtained compatible base ROM. TEON releases do
not include commercial game ROM bytes.
