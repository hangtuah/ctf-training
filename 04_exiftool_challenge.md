# Bahagian 4 - Exiftool challenge (stego basic)

Objektif:
- Peserta kenal metadata.
- Peserta tahu baca metadata menggunakan exiftool.

Lokasi:
- `03_stego/exif_metadata`

Command:
- `cd ~/workshop/03_stego/exif_metadata`
- `exiftool picture.jpg | grep FLAG`

Apa berlaku?
- exiftool baca metadata (Comment, Author, Description).
- Flag disimpan dalam metadata Comment.

Output contoh:
- `Comment : FLAG{metadata_treasure}`

Nota:
- Challenge paling mudah dan cepat bagi keyakinan awal.
