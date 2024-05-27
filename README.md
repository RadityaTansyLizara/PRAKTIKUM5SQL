# PRAKTIKUM5SQL
| Variable | Isi |
| -------- | --- |
| Nama | RADITYA TANSY LIZARA  |
| NIM | 312310454 |
| Kelas | TI.23.A5 |
| Mata Kuliah | Basis Data |

## Latihan

- Lakukan JOIN table Mahasiswa dan Dosen.
- Lakukan JOIN tabel Matakuliah dan Dosen.
- Lakukan JOIN table JadwalMengajar, Dosen, dan Matakuliah.
- Lakukan JOIN tabel KrsMahasiswa, Mahasiswa, Matakuliah, dan Dosen.

## Buat Script SQL JOIN Table berdasarkan skema data diatas.
```
INSERT INTO mahasiswa VALUES
    (1812345, 'Ari Santoso', 'L', '1999-10-11', NULL, 'Bekasi', NULL, NULL, 'DS002'),
    (1823456, 'Dina Marlina', 'P', '1998-11-20', NULL, 'Jakarta', NULL, NULL, NULL),
    (1834567, 'Rahmat Hidayat', 'L', '1999-05-10', NULL, 'Bekasi', NULL, NULL, NULL),
    (1845678, 'Jaka Sampurna', 'L', '2000-10-19', NULL, 'Cikarang', NULL, NULL, NULL),
    (1856789, 'Tia Lestari', 'P', '1999-02-15', NULL, 'Karawang', NULL, NULL, NULL),
    (1867890, 'Anton Sinaga', 'L', '1998-06-22', NULL, 'Bekasi', NULL, NULL, NULL),
    (1912345, 'Listia Nastiti', 'P', '2001-10-23', NULL, 'Jakarta', NULL, NULL, NULL),
    (1923456, 'Amira Jarisa', 'P', '2001-01-24', NULL, 'Karawang', NULL, NULL, 'DS004'),
    (1934567, 'Laksana Mardito', 'L', '1999-04-14', NULL, 'Cikarang', NULL, NULL, NULL),
    (1945678, 'Jura Marsina', 'P', '2000-05-10', NULL, 'Cikarang', NULL, NULL, NULL),
    (1956789, 'Dadi Martani', 'L', '2001-08-29', NULL, 'Bekasi', NULL, NULL, 'DS005'),
    (1967890, 'Bayu Laksono', 'L', '1999-07-22', NULL, 'Cikarang', NULL, NULL, 'DS004');

SELECT*FROM Mahasiswa;
`````
Output :
![image](https://github.com/RadityaTansyLizara/PRAKTIKUM5SQL/assets/147571863/9ba09f49-9cc2-42b6-865a-1ee67424e6e5)


`````
INSERT INTO Matakuliah VALUES
('MK001', 'Algoritma Dan Pemrogaman', 3),
('MK002', 'Praktikum Algoritma Dan Pemrograman', 1),
('MK003', 'Teknologi Basis Data', 3),
('MK004', 'Praktikum Teknologi Basis Data', 1),
('MK005', 'Pemrograman Dasar', 3),
('MK006', 'Pemrograman Berorientasi Objek', 3),
('MK007', 'Struktur Data', 3),
('MK008', 'Arsitektur Komputer', 2);

SELECT * FROM Matakuliah;
`````
Output :
![image](https://github.com/RadityaTansyLizara/PRAKTIKUM5SQL/assets/147571863/ce764984-8768-4c13-ad3e-eb5b69df6ac9)


`````
INSERT INTO JadwalMengajar VALUES
('MK001', 'DS002', 'Senin', '10:00:00', '102'),
('MK002', 'DS002', 'Senin', '13:00:00', 'Lab. 01'),
('MK003', 'DS001', 'Selasa', '08:00:00', '201'),
('MK004', 'DS001', 'Rabu', '10:00:00', 'Lab. 02'),
('MK005', 'DS003', 'Selasa', '10:00:00', 'Lab. 01'),
('MK006', 'DS004', 'Kamis', '09:00:00', 'Lab. 03'),
('MK007', 'DS005', 'Rabu', '08:00:00', '102'),
('MK008', 'DS005', 'Kamis', '13:00:00', '201');

SELECT*FROM JadwalMengajar;
`````
Output :
GAMBAR

`````
INSERT INTO KRSMahasiswa VALUES
(1823456, 'MK001', 'DS002', 3, NULL),
(1823456, 'MK002', 'DS002', 1, NULL),
(1823456, 'MK003', 'DS001', 3, NULL),
(1823456, 'MK004', 'DS001', 3, NULL),
(1823456, 'MK007', 'DS005', 3, NULL),
(1823456, 'MK008', 'DS005', 3, NULL);

SELECT * FROM KRSMahasiswa;
`````
Output :
GAMBAR

# Latihan
- JOIN table Mahasiswa dan Dosen
`````
SELECT Mahasiswa.nim, Mahasiswa.nama, Mahasiswa.jk, Dosen.nama AS "Dosen PA"
FROM Mahasiswa INNER JOIN Dosen ON Dosen.kd_ds = Mahasiswa.kd_ds;
`````
Output :
GAMBAR

- LEFT JOIN table Mahasiswa dan Dosen
`````
SELECT Mahasiswa.nim, Mahasiswa.nama, Mahasiswa.jk, Dosen.nama AS "Dosen PA"
FROM Mahasiswa LEFT JOIN Dosen ON Dosen.kd_ds = Mahasiswa.kd_ds;
`````
Output:
GAMBAR

- JOIN table Jadwal Mengajar, Dosen, dan Matakuliah
`````
SELECT Matakuliah.kd_mk, Matakuliah.nama, Matakuliah.sks, Dosen.nama AS "Dosen Pengampu"
FROM JadwalMengajar
LEFT JOIN Matakuliah ON JadwalMengajar.kd_mk = Matakuliah.kd_mk
LEFT JOIN Dosen ON JadwalMengajar.kd_ds = Dosen.kd_ds;
`````
Output:
GAMBAR

- JOIN table JadwalMengajar, Dosen, dan Matakuliah
`````
SELECT Matakuliah.kd_mk, Matakuliah.nama, Matakuliah.sks, Dosen.nama AS "Dosen Pengampu", JadwalMengajar.hari, JadwalMengajar.jam, JadwalMengajar.ruang
FROM JadwalMengajar
LEFT JOIN Matakuliah ON JadwalMengajar.kd_mk = Matakuliah.kd_mk
LEFT JOIN Dosen ON JadwalMengajar.kd_ds = Dosen.kd_ds;
`````
Output :
GAMBAR

- JOIN tabel KRSMahasiswa, Mahasiswa, Matakuliah, dan Dosen
`````
SELECT Mahasiswa.nim, Mahasiswa.nama AS "nama", Dosen.nama AS "Dosen PA", Matakuliah.nama AS "Matakuliah", Matakuliah.sks, Dosen.nama AS "Dosen Pengampu"
FROM KRSMahasiswa
JOIN Mahasiswa ON KRSMahasiswa.nim = Mahasiswa.nim
JOIN Matakuliah ON KRSMahasiswa.kd_mk = Matakuliah.kd_mk
JOIN Dosen ON KRSMahasiswa.kd_ds = Dosen.kd_ds;
`````
Output :
GAMBAR
