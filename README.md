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

```
#### Contoh Respon JSON:
```bash
{
  "📍 Kota": "Jakarta",
  "🌡️ Suhu Saat Ini": "30°C",
  "💧 Kelembaban": "80%",
  "💨 Kecepatan Angin": "15 km/h",
  "🧭 Arah Angin": "45°",
  "🕒 Update": "2025-03-25T10:00:00Z",
  "📅 Prediksi Cuaca": [
    {
      "📆 Tanggal": "2025-03-26",
      "🌡️ Suhu Max": "32°C",
      "🌡️ Suhu Min": "24°C",
      "💧 Kelembaban Max": "85%",
      "💧 Kelembaban Min": "75%",
      "🌧️ Curah Hujan": "5 mm",
      "💨 Angin Max": "20 km/h",
      "💨 Angin Min": "10 km/h"
    }
  ],
  "grafik": "data:image/png;base64,..."
}

```
### Format Text:
```bash
🌍 **Cuaca di Jakarta**:
🌡️ Suhu Saat Ini: 30°C
💧 Kelembaban: 80%
💨 Kecepatan Angin: 15 km/h
🕒 Update: 2025-03-25T10:00:00Z

🔮 **Prediksi Cuaca:**
📆 2025-03-26 | 🌡️ 32°C - 24°C | 💧 85% - 75% | 🌧️ 5 mm | 💨 20 km/h - 10 km/h

```

# AstraWeather API:
```bash
https://astraasia.github.io/astraweather/index.html
