# Bahagian 5 - Binwalk challenge (forensics intermediate)

Objektif:
- Peserta belajar extract file tersembunyi.
- Kenal konsep embedded data dalam file.

Lokasi:
- `04_forensics/binwalk_hidden_zip`

Command:
- `cd ~/workshop/04_forensics/binwalk_hidden_zip`
- `binwalk -e image_like.png`
- `cat _image_like.png.extracted/hidden_flag.txt`

Apa berlaku?
- `binwalk -e` auto extract ZIP dalam "fake" PNG.
- Dalam ZIP ada file text mengandungi flag.

Output:
- `FLAG{hidden_zip_found}`

Nota fasilitator:
- Ajar peserta buka folder yang binwalk hasilkan.
- Tekankan systematically explore.
