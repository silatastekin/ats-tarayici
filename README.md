# ats-tarayici

# ATS CV & Job Posting Matcher

Bu proje, PDF formatındaki bir CV ile iş ilanı metnini karşılaştırarak adayın ilana ne kadar uygun olduğunu analiz eden basit bir ATS asistanıdır.

Uygulama; CV içeriğini PDF dosyasından okur, iş ilanı metniyle karşılaştırır ve yerel olarak çalışan Ollama modeli üzerinden analiz üretir.

---

# Özellikler

- PDF CV yükleme
- İş ilanı metni girme
- CV ve ilan arasında teknik beceri karşılaştırması
- Uyum skoru üretme
- Güçlü yönleri listeleme
- İş ilanında olup CV’de bulunmayan eksik anahtar kelimeleri gösterme
- Türkçe analiz sonucu üretme
- API key gerektirmeden lokal LLM ile çalışma

---

# Kullanılan Teknolojiler

- HTML
- CSS
- JavaScript
- PDF.js
- Ollama
- Gemma 3 4B modeli

---

# Proje Mantığı

Uygulama şu adımlarla çalışır:

1. Kullanıcı PDF formatında CV yükler.
2. Kullanıcı iş ilanı metnini ilgili alana yapıştırır.
3. PDF.js, CV içindeki metni çıkarır.
4. JavaScript, CV metnini ve iş ilanı metnini Ollama API’ye gönderir.
5. Lokal LLM modeli CV ile iş ilanını karşılaştırır.
6. Sonuç ekranda skor, güçlü yönler ve eksik anahtar kelimeler olarak gösterilir.

# Eksik Anahtar Kelime Mantığı

Bu projede eksik anahtar kelimeler şu kurala göre hesaplanır:

Eksik = İş ilanında istenen ama CV’de bulunmayan beceriler

Kurulum

Öncelikle projeyi bilgisayarına indir:

git clone https://github.com/kullanici-adi/proje-adi.git
cd proje-adi
Ollama Kurulumu

Bu proje lokal LLM kullandığı için Ollama kurulu olmalıdır.

Ollama’yı buradan indirebilirsin:

https://ollama.com

Kurulumdan sonra terminal veya CMD açıp şu komutu çalıştır:

ollama serve

Ardından projede kullanılan modeli indir:

ollama pull gemma3:4b

Modelin yüklendiğini kontrol etmek için:

ollama list

Test etmek için:

ollama run gemma3:4b
Çalıştırma

Bu proje tek dosyalık bir frontend uygulamasıdır.

index.html dosyasını tarayıcıda açman yeterlidir.

Daha stabil çalıştırmak için VS Code içinde Live Server eklentisiyle açabilirsin.

Önemli Not

Ollama çalışmıyorsa analiz başlamaz.

Bu yüzden uygulamayı kullanmadan önce şu komut açık kalmalıdır:

ollama serve

Uygulama Ollama’ya şu lokal API adresinden istek gönderir:

http://localhost:11434/api/generate
Model Değiştirme

Varsayılan model:

const MODEL = 'gemma3:4b';

Farklı bir model kullanmak istersen önce modeli indir:

ollama pull llama3.2

Sonra kodda model adını değiştir:

const MODEL = 'llama3.2';
Ekran Çıktısı

Uygulama analiz sonucunda şu bilgileri gösterir:

Uyum skoru
Genel özet
Güçlü yönler
Eksik anahtar kelimeler
Güvenlik ve Gizlilik

Bu proje API key kullanmaz.

CV ve iş ilanı metni dış bir servise gönderilmez.

Analiz, kullanıcının kendi bilgisayarında çalışan Ollama modeliyle yapılır.

Geliştirilebilir Özellikler
Sonuçları PDF olarak indirme
Daha detaylı ATS raporu üretme
CV iyileştirme önerileri ekleme
Çoklu CV karşılaştırma
İş ilanından otomatik anahtar kelime çıkarma
React veya Vue ile daha gelişmiş arayüz
Backend ekleyerek analiz geçmişi kaydetme
Proje Durumu

Bu proje geliştirme aşamasındadır.

Temel amaç, lokal LLM kullanarak CV ve iş ilanı eşleştirmesi yapan basit ve anlaşılır bir ATS analiz aracı geliştirmektir.

Lisans

Bu proje eğitim ve kişisel geliştirme amacıyla hazırlanmıştır.
