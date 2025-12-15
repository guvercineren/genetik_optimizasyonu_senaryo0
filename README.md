# BLG 307 - Yapay Zeka Sistemleri | Proje 1: Genetik Algoritma ile Optimizasyon

## Senaryo 0: Akıllı Depoda Raf Yüksekliği ve Derinliği Ayarı

Bu proje, öğrenci numaramın son hanesine göre belirlenen Senaryo 0'ın çözümünü içerir. Amacım, **Genetik Algoritma (GA)** kullanarak bir lojistik firmasının depo verim puanını (y) maksimize etmektir. Optimizasyon kısıtları, Penaltı Yöntemi kullanılarak GA'ya entegre edilmiştir.

### 1. Problem Tanımı

- **Öğrenci Ad/Soyad/No:** Eren Güvercin / 2212729010
- **Amaç Fonksiyonu (Maksimize Edilecek y):** $$y = 4x_1 + 3x_2 - 0.5x_1x_2$$
- **Değişkenler:**
    - $x_1$: Raf yüksekliği $(m) \in [2, 6]$
    - $x_2$: Raf derinliği $(m) \in [1, 4]$
- **Kısıtlar:**
    1. Alan Sınırı: $x_1 + x_2 \le 8$
    2. Minimum Derinlik: $x_2 \ge 1.5$

### 2. Uygulanan Algoritma ve Parametreler

Çözüm, Gerçel Sayı Temsili (Real-valued encoding) ile geliştirilmiş bir Genetik Algoritma kullanılarak bulunmuştur.

| GA Operatörü | Yöntem | Parametre |
| :--- | :--- | :--- |
| **Birey Temsili** | Gerçel Sayı Dizisi | $[x_1, x_2]$ |
| **Seçilim** | Turnuva Seçilimi | $k=5$ |
| **Çaprazlama** | Aritmetik Ortalama Çaprazlama | Oran: 0.8 |
| **Mutasyon** | Düzgün Mutasyon (Uniform Mutation) | Oran: 0.1 |
| **Kısıt Yönetimi** | Penaltı Yöntemi | Katsayı: 5000 |
| **Popülasyon/İterasyon** | Pop: 100, İterasyon: 200 | |

### 3. Optimum Sonuçlar ve Analiz

Algoritmanın çalıştırılmasıyla bulunan en iyi çözüm şudur:

- **Optimum $x_1$ (Raf Yüksekliği):** **5.9428** m
- **Optimum $x_2$ (Raf Derinliği):** **2.0568** m
- **Maksimum Depo Verim Puanı (y):** **23.8277**

**Kısıt Kontrolü:** $x_1 + x_2 = 7.9996 \le 8$ (Uygun), $x_2 = 2.0568 \ge 1.5$ (Uygun).

**Yorum:** Algoritma, teorik optimuma çok yakın bir çözüm bulmuştur. Özellikle, $x_1 + x_2$ toplamının üst kısıt olan 8'e ($7.9996$) son derece yakın olması, algoritmanın kısıtlanmış alanı verimli kullandığını ve çözümün bu kısıtın üzerinde oluştuğunu göstermektedir.

### 4. Kodun Çalıştırılması

1.  Gerekli Python kütüphanelerinin (NumPy, Matplotlib) kurulu olduğundan emin olun.
2.  `Genetik_Optimizasyon_Senaryo0.ipynb` dosyasını Jupyter Notebook ortamında açın.
3.  Tüm hücreleri sırasıyla çalıştırın.






















