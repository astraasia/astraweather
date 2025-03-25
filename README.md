# AstraWeather API

AstraWeather API memberikan informasi cuaca **real-time** dan **prediksi cuaca** hingga 7 hari ke depan. API ini menggunakan data dari **Open-Meteo** dan menyediakan berbagai informasi seperti suhu, kelembaban, kecepatan angin, curah hujan, serta grafik suhu harian.

## Fitur Utama

- **Cuaca Saat Ini**: Menampilkan data cuaca terkini.
- **Prediksi Cuaca 7 Hari**: Informasi cuaca hingga 7 hari ke depan.
- **Unit Kecepatan Angin**: Pilihan antara `km/h` atau `m/s`.
- **Grafik Suhu**: Visualisasi grafik suhu harian dalam format base64.

## Endpoint

### `/cuaca/`

Endpoint ini digunakan untuk mengambil data cuaca berdasarkan **latitude** dan **longitude**.

#### Parameter Query:
| Parameter     | Tipe     | Deskripsi                                                      |
|---------------|----------|----------------------------------------------------------------|
| `kota`        | string   | Nama kota (contoh: Jakarta)                                    |
| `lat`         | float    | Latitude (-90 hingga 90)                                        |
| `lon`         | float    | Longitude (-180 hingga 180)                                     |
| `hari`        | integer  | Jumlah hari untuk prediksi cuaca (1-7, default 1)              |
| `format`      | string   | Format output: `json` atau `text` (default: `json`)            |
| `unit_angin`  | string   | Unit kecepatan angin: `km/h` atau `m/s` (default: `km/h`)      |

#### Contoh Request:
```bash
GET https://api.astracloud.com/cuaca/?kota=Jakarta&lat=-6.1751&lon=106.8650&hari=3&format=json&unit_angin=km/h
