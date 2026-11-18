# GitHub kurulum adımları

Bu dosya mevcut GitHub repository'sine uygulanacak adımları içerir. Zaten repo açtıysanız ikinci bir repo oluşturmayın.

## Repo ve açıklama

1. Repo ana sayfasında About yanındaki dişliye tıklayın.
2. Description alanına “Raspberry Pi 4 Model B için 64-bit AArch64 topluluk işletim sistemi çekirdeği” yazın.
3. Topics olarak raspberry-pi, raspberry-pi-4, aarch64, operating-system, kernel, bare-metal ekleyin.
4. Katkı almak için repo görünürlüğünü Public yapın.
5. Settings → General → Features altında Issues açık kalsın; Discussions da açın.

## Dosyaları yükleme

Repo ana sayfasında Add file → Upload files ile bu paketin içindeki dosyaları yükleyin. Klasörün kendisini seçemiyorsanız GitHub Desktop kurup Clone repository ile repo'yu bilgisayarınıza alın, dosyaları repo klasörüne kopyalayın, GitHub Desktop'ta değişiklikleri commit edip Push origin seçin.

İlk commit mesajı: docs: add Raspberry Pi 4B 64-bit project starter

## Etiketleri oluşturma

Issues → Labels → New label üzerinden şunları ekleyin:

| Etiket | Ne için |
| --- | --- |
| good first issue | Yeni başlayanlara uygun küçük iş |
| help wanted | Ek katkı beklenen iş |
| docs | Rehber ve belge |
| kernel | Çekirdek kodu |
| hardware | Pi 4B/UART/GPIO |
| design | Teknik karar veya araştırma |
| blocked | Başka karar/iş bekliyor |

.github/ISSUE_TEMPLATE klasöründeki şablonlar issue açarken görünür.

## İlk issue'ları aç

Her birini Issues → New issue ile ayrı açın:

1. Pi 4B bootloader ve kernel giriş sözleşmesini doğrula — design, help wanted
2. Windows/WSL için AArch64 bare-metal araç zinciri rehberi yaz — docs, good first issue
3. UART0/PL011 ve UART1/mini UART seçim issue'su — hardware, design
4. AArch64 kernel giriş kodu için ilk çalışma taslağı — kernel
5. Gerçek Pi 4B'de boot test kontrol listesi — hardware, docs

Issue içine amaç, tamamlanma ölçütü ve nasıl test edileceğini yazın. Bu dosya sadece başlangıç başlıklarını veriyor; ayrıntılı iş tanımını issue açarken ekleyin.

## Project panosu

1. GitHub profil fotoğrafı → Your profile → Projects → New project.
2. Board seçin; adı Pi4OS geliştirme panosu olsun.
3. Board'a repo issue'larını ekleyin.
4. Durumları Backlog, Ready, In progress, Review, Done olarak kullanın.
5. Her iş kartının bir issue'ya bağlı kalmasını sağlayın.

## Sohbet ve katkı

- Teknik soru ve fikir: Discussions.
- Hata, yapılacak iş ve teknik karar: Issues.
- Değişiklik: branch veya fork üzerinden Pull Request.
- Herkese doğrudan yazma izni vermeyin; repo'yu yöneten kişilere sınırlayın. Dış katkı sahipleri PR açabilir.

Derleme komutu gerçekten çalışır hale geldikten sonra Actions ile her PR'de build kontrolü ekleyin. İlk günden çalışmayan CI kurmayın.
