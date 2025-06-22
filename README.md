![image](https://github.com/user-attachments/assets/4fc3e72f-2acd-4123-b092-4a4fb7eba30e)


Haftalık Otomatik Web Site SWOT Analizi (n8n Workflow)

Bu n8n workflow, belirli bir web sitesinin HTML içeriğini ve Google PageSpeed performans skorunu analiz ederek haftalık olarak bir **SWOT analizi** oluşturur ve sonuçları e-posta ile gönderir.

---

## 📌 Özellikler

- ⏰ **Otomatik Çalışma**: Workflow, her hafta Pazartesi günü saat 10:00'da tetiklenir.
- 🌐 **Web Site HTML Çekme**: Belirlenen URL'den HTML içeriği çekilir.
- 🚀 **PageSpeed API ile Performans Analizi**: Google PageSpeed API kullanılarak performans skorları alınır.
- 🧠 **AI ile SWOT Analizi**: Gemini AI (Langchain üzerinden) kullanılarak içerik ve performans verilerine dayalı SWOT analizi hazırlanır.
- 📬 **E-posta Gönderimi**: SWOT analizi, tanımlı e-posta adresine gönderilir.
- 🧪 **Kod Node ile Özelleştirme**: Veri işleme ve özetleme için JavaScript kodu içerir.

---

## 🧱 Kullanılan Node'lar

| Node Adı                | Görev                                   |
|--------------------------|------------------------------------------|
| `Schedule Trigger`       | Haftalık tetikleme                        |
| `html_excerpt`           | Web sitesinden HTML çekme (HTTP Request) |
| `pagespeed_summary`      | Google PageSpeed API çağrısı             |
| `Merge`                  | HTML ve performans verilerini birleştirme|
| `Code`                   | Verileri sadeleştirme / dönüştürme       |
| `Google Gemini Chat Model` | Gemini 2.5 üzerinden LLM çalıştırma    |
| `Basic LLM Chain`        | Prompt ile SWOT analizi oluşturma        |
| `Send Email`             | SWOT çıktısını e-posta ile gönderme      |

---

## ⚙️ Kurulum Talimatları

### 1. n8n ortamında bu adımları takip et:

1. JSON dosyasını n8n'e import edin:
   - `Workflows > Import > From File or Clipboard`

2. `Send Email` node içindeki **SMTP Credentials** kısmını kendi e-posta sağlayıcınıza göre yapılandırın.
   - Gmail kullanıyorsanız, [App Password](https://myaccount.google.com/apppasswords) kullanmalısınız.

3. `pagespeed_summary` node içinde `YOUR_API_KEY` kısmını kendi **Google PageSpeed API anahtarınız** ile değiştirin:
   - [API Anahtarı Alma](https://developers.google.com/speed/docs/insights/v5/get-started)

4. `Google Gemini Chat Model` node'unda kendi Google PaLM API erişim bilgilerinizi kullanın.

---

## 🔐 Gereksinimler

- Google PageSpeed API Key
- Gemini (Google) API erişimi (PaLM/Gemini 1.5/2.5 üzerinden)
- SMTP destekleyen bir e-posta hesabı




