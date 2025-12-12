# Vehicle Engine Status Include for SA-MP

## Deskripsi Singkat (Bahasa Indonesia)

Include Pawn ini berfungsi untuk **mengecek dan mengatur status mesin kendaraan** (On/Off) di SA-MP (San Andreas Multiplayer), agar dapat digunakan pada script mode atau filterscript Anda. Sudah disediakan variable dan fungsi siap pakai, dapat diubah sesuai kebutuhan sistem engine di server Anda.

## Fitur

- Menyediakan variable global status mesin kendaraan (`VehicleEngineStatus[MAX_VEHICLES]`)
- Fungsi untuk:
  - Mengecek apakah mesin kendaraan menyala (`IsVehicleEngineOn(vehicleid)`)
  - Mengatur status mesin kendaraan (`SetVehicleEngineStatus(vehicleid, status)`)
- Siap modifikasi dan integrasi dengan sistem engine Anda.
- Contoh command sudah ada (dalam komentar).

## Cara Penggunaan

1. **Pasang include ini di script utama Anda (e.g. gamemode.pwn atau filterscript).**
2. **Pastikan variable `VehicleEngineStatus[MAX_VEHICLES]` tidak ganda jika sudah ada.**
3. **Panggil `IsVehicleEngineOn(vehicleid);` untuk mengecek status mesin kendaraan.**
4. **Panggil `SetVehicleEngineStatus(vehicleid, status);` untuk mengubah status mesin kendaraan.**
5. **Contoh implementasi command ada dalam komentar di akhir file.**

## Contoh Kode Sederhana

```pawn
// Cek status engine kendaraan player
CMD:cekengine(playerid, params[])
{
    if(!IsPlayerInAnyVehicle(playerid)) return SendClientMessage(playerid, -1, "Kamu tidak di dalam kendaraan!");
    new vehicleid = GetPlayerVehicleID(playerid);
    new eng = IsVehicleEngineOn(vehicleid);
    if(eng == 1)
        SendClientMessage(playerid, -1, "Mesin kendaraan SAAT INI: AKTIF / NYALA.");
    else if(eng == 0)
        SendClientMessage(playerid, -1, "Mesin kendaraan SAAT INI: MATI.");
    else
        SendClientMessage(playerid, -1, "Status kendaraan tidak valid.");
    return 1;
}
```

## Penyesuaian

- Silakan sesuaikan fungsi getter/setter atau array status jika engine system Anda berbeda (Lihat bagian komentar di atas fungsi).
- Bisa digabungkan dengan script jendela dan doorsystem, atau sistem kendaraan lainnya.

## Credits

Script ini dibuat oleh **Raihan Purnawadi**  
Feel free to use, share, and modify, as long as the original credit remains!

## License

Open Source, boleh digunakan dan dimodifikasi untuk kebutuhan server roleplay atau freeroam Anda. Jangan hapus kredit pembuat.
