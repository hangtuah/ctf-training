# Bahagian 1 - Mula guna server (SSH + salin challenge)

Objektif:
- Peserta berjaya login server.
- Peserta tahu cara salin challenge ke folder sendiri.
- Peserta selesa dengan filesystem Linux.

Command yang digunakan:
- ssh groupXX@IP_SERVER
- pwd
- ls
- mkdir workshop
- cp -r /opt/ctf/challenges/* ~/workshop
- cd workshop

Flow:
1. Peserta login: `ssh group01@IP_SERVER`
2. Buka directory home: `pwd`
3. Buat folder latihan: `mkdir workshop`
4. Salin challenge: `cp -r /opt/ctf/challenges/* ~/workshop`
5. Masuk folder: `cd workshop`

Nota fasilitator:
- Pastikan semua peserta boleh buat `cp -r` tanpa permission error.
