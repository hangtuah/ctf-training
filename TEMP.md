===========================================================
     CAPTURE THE FLAG WORKSHOP – FLOW & TRAINING SCRIPT
===========================================================

BAHAGIAN 0 — PENGENALAN (TEORI)
--------------------------------
Objektif:
- Peserta faham apa itu CTF, format pertandingan & cara submit flag.
- Bina mindset "explore, test, break, solve".

Isi kandungan:
1. Apa itu CTF?
   - Pertandingan keselamatan siber.
   - Konsep: cari flag tersembunyi dalam file/sistem.
   - Flag format biasa: FLAG{something} / CTF{something}

2. Format pertandingan:
   - Jeopardy-style (kategori & poin)
   - Attack-defense (advance, tidak cover di bengkel)
   - Forensics, Stego, Crypto, Web, Misc

3. Cara submit flag:
   - Copy flag → paste dalam platform
   - Case sensitive
   - Tidak ubah format flag

4. Tools yang digunakan dalam bengkel:
   - strings
   - exiftool
   - binwalk
   - steghide
   - Linux basic commands

===========================================================
BAHAGIAN 1 — MULA GUNA SERVER (SSH + SALIN CHALLENGE)
===========================================================
Objektif:
- Peserta berjaya login server.
- Peserta tahu cara salin challenge ke folder sendiri.
- Peserta selesa dengan filesystem Linux.

Command yang digunakan:
  ssh groupXX@IP_SERVER
  pwd
  ls
  mkdir workshop
  cp -r /opt/ctf/challenges/* ~/workshop
  cd workshop

Flow:
1. Peserta login: 
     ssh group01@IP_SERVER
2. Buka directory home:
     pwd
3. Buat folder latihan:
     mkdir workshop
4. Salin challenge:
     cp -r /opt/ctf/challenges/* ~/workshop
5. Masuk folder:
     cd workshop

Nota Fasilitator:
- Confirm semua peserta boleh buat cp -r tanpa permission error.

===========================================================
BAHAGIAN 2 — LINUX COMMAND BASIC (ESSENTIAL UNTUK CTF)
===========================================================
Objektif:
- Peserta boleh navigate file & guna command untuk analisis.
- Ini adalah asas untuk semua challenge selepas ini.

Command diperkenalkan:
  ls, cd, cat, file, strings, grep, head, tail, pwd

Mini latihan:
1. Tunjuk isi folder:
     ls -l
2. Baca file:
     cat filename.txt
3. Guna grep:
     cat filename.txt | grep keyword

===========================================================
BAHAGIAN 3 — STRINGS CHALLENGE (FORENSICS BASIC)
===========================================================
Objektif:
- Peserta faham kegunaan 'strings' untuk cari text tersembunyi.
- Dapat jumpa flag pertama.

Lokasi challenge:
  01_intro/strings_basic

Command:
  cd ~/workshop/01_intro/strings_basic
  strings secret.bin | grep FLAG

Apa yang berlaku?
- strings mengekstrak readable text dalam file binary.
- Flag memang tersembunyi sebagai plaintext.

Expected output:
  FLAG{strings_is_easy}

Nota Fasilitator:
- Tekankan konsep "explore dulu, baru solve".

===========================================================
BAHAGIAN 4 — EXIFTOOL CHALLENGE (STEGO BASIC)
===========================================================
Objektif:
- Peserta kenal metadata.
- Peserta tahu baca metadata menggunakan exiftool.

Lokasi:
  03_stego/exif_metadata

Command:
  cd ~/workshop/03_stego/exif_metadata
  exiftool picture.jpg | grep FLAG

Apa berlaku?
- exiftool baca metadata (Comment, Author, Description)
- Flag disimpan dalam metadata Comment.

Output contoh:
  Comment : FLAG{metadata_treasure}

Nota:
- Ini challenege paling mudah & cepat bagi keyakinan awal.

===========================================================
BAHAGIAN 5 — BINWALK CHALLENGE (FORENSICS INTERMEDIATE)
===========================================================
Objektif:
- Peserta belajar extract file tersembunyi.
- Kenal konsep "embedded data" dalam file.

Lokasi:
  04_forensics/binwalk_hidden_zip

Command:
  cd ~/workshop/04_forensics/binwalk_hidden_zip
  binwalk -e image_like.png
  cat _image_like.png.extracted/hidden_flag.txt

Apa berlaku?
- `binwalk -e` auto extract ZIP dalam "fake" PNG.
- Dalam zip ada file text mengandungi flag.

Output:
  FLAG{hidden_zip_found}

Nota:
- Ajar peserta buka folder yang binwalk hasilkan.
- Tekankan systematically explore.

===========================================================
BAHAGIAN 6 — STEGHIDE CHALLENGE (STEGO INTERMEDIATE)
===========================================================
Objektif:
- Peserta boleh extract hidden file dengan password.
- Faham konsep embedding data dalam image/audio.

Lokasi:
  03_stego/steghide_basic

Command:
  cd ~/workshop/03_stego/steghide_basic
  steghide extract -sf cover.jpg -p password123
  cat message.txt

Apa berlaku?
- steghide embed message → peserta extract balik.
- Password diperlukan (diberikan dalam README).

Expected output:
  FLAG{simple_stego_flag}

Nota:
- Ini challenge real-world yang selalu ada dalam CTF Malaysia.

===========================================================
BAHAGIAN 7 — MINI CTF (COMBINED SKILLS)
===========================================================
Objektif:
- Peserta apply semua teknik yang sudah belajar.
- Mereka berlatih solve challenge tanpa clue terus.
- Bina confidence sebelum masuk pertandingan sebenar.

Mini CTF boleh mengandungi:
- 1 challenge strings
- 1 challenge metadata
- 1 challenge binwalk
- 1 challenge steghide
- 1 challenge mystery file (untuk recap)

Flow:
1. Fasilitator lepaskan challenge.
2. Peserta cuba dalam masa 10–15 minit.
3. Discuss solution di projector.

===========================================================
BAHAGIAN 8 — CLOSING
===========================================================
Objektif:
- Peserta faham bahawa CTF bukan “hacker”, tetapi “analysis skill”.
- Beri tips sambung belajar kategori lain (web exploitation, network, crypto advanced).

Tips:
- Ambil bahagian di Malaysia CTF (TWO, CyberX, MyCTF, HITBGSEC)
- Join platform:
  - picoCTF
  - TryHackMe
  - HackTheBox
  - root-me.org

===========================================================
TAMAT FLOW LATIHAN CTF BEGINNER
===========================================================
