# Bahagian 6 - Steghide challenge (stego intermediate)

Objektif:
- Peserta boleh extract hidden file dengan password.
- Faham konsep embedding data dalam image/audio.

Lokasi:
- `03_stego/steghide_basic`

Command:
- `cd ~/workshop/03_stego/steghide_basic`
- `steghide extract -sf cover.jpg -p password123`
- `cat message.txt`

Apa berlaku?
- steghide embed message dan peserta extract balik.
- Password diperlukan (diberikan dalam README).

Expected output:
- `FLAG{simple_stego_flag}`

Nota:
- Challenge real-world yang selalu ada dalam CTF Malaysia.
