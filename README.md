# ARES-Realtime-Proxy (AI Risk Evaluation Suite)
> **Professional AI Penetration Testing & Real-time Offensive Tool**

ARES-Realtime-Proxy adalah toolkit keamanan siber ofensif yang dirancang untuk menguji kerentanan pada infrastruktur Large Language Models (LLM) dan endpoint AI. Terinspirasi dari riset keamanan terbaru, tool ini mengotomatisasi proses *Prompt Injection*, *Credential Extraction*, dan *Anonymous Validation*.

---

## 🛡️ Kesimpulan Kerentanan (Vulnerability Summary)
Berdasarkan hasil audit dan riset pada repository terkait, tool ini fokus pada eksploitasi celah keamanan berikut:

1. **Indirect Prompt Injection**: Memanipulasi instruksi sistem melalui input pengguna yang disamarkan.
2. **Data Leakage (PII/Credentials)**: Kebocoran kunci API (OpenAI, Gemini, dll) dan kredensial database melalui respon AI.
3. **Guardrail Bypass**: Penggunaan teknik mutasi (Base64, Sudo Mode) untuk melewati filter keamanan konten.
4. **Unauthorized Extraction**: Pengambilan data sensitif dari variabel lingkungan (Environment Variables) yang terekspos ke logika model.

---

## 🚀 Fitur Utama

* **Anonymous Scanning**: Mendukung routing melalui jaringan Tor/Socks5 untuk menyembunyikan IP asli.
* **Payload Mutation Engine**: Mengubah intent serangan secara dinamis menggunakan berbagai teknik *obfuscation*.
* **Real-time Looting**: Ekstraksi otomatis kunci API dan password menggunakan Regex yang dioptimalkan.
* **Auto-Validator**: Memverifikasi secara instan apakah kunci yang dicuri masih aktif (Valid/Live).
* **CLI Integration**: Antarmuka baris perintah yang ramah untuk pengguna Kali Linux.

---

## 🛠️ Instalasi & Persyaratan

Pastikan Anda memiliki Python 3.x dan dependensi berikut:
pip3 install requests colorama

Untuk fitur anonimitas penuh, pastikan layanan Tor berjalan:
sudo service tor start

# Panduan Penggunaan
1. Mode Bantuan (Help)
Melihat seluruh kapabilitas dan argumen yang tersedia: 
python3 ARES-Realtime-Proxy.py -h

2. Scanning Target Real-time
Melakukan serangan langsung ke endpoint target:

python3 ARES-Realtime-Proxy.py -u [https://target-ai.com/api/v1/chat](https://target-ai.com/api/v1/chat)

3. Scanning Anonim (via Tor)
Menjalankan pengujian tanpa mengungkap identitas asli:

python3 ARES-Realtime-Proxy.py -u [https://target-ai.com](https://target-ai.com) -p socks5://127.0.0.1:9050

4. Mode Verbose
Melihat detail pengiriman payload dan respon mentah:
python3 ARES-Realtime-Proxy.py -u [https://target.com](https://target.com) -v

# Hasil Temuan (Loot)
Semua temuan sensitif yang tervalidasi akan disimpan secara otomatis dalam file:
ares_loot.log

# SERVER YANG DI DUKUNG 
KALI LINUX 
LINUX 

⚠️ Disclaimer
Penggunaan tool ini hanya diperuntukkan bagi Ethical Hacking, pengujian penetrasi resmi, dan riset keamanan. Penulis tidak bertanggung jawab atas penyalahgunaan atau kerusakan yang disebabkan oleh alat ini. Gunakan dengan penuh tanggung jawab.

```bash
pip3 install requests colorama
