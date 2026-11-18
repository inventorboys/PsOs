# Raspberry Pi 4B 64-bit İşletim Sistemi

Pi 4 Model B üzerinde çalışan, toplulukla geliştirilen eğitim amaçlı bir işletim sistemi çekirdeği.

## Projenin ilk hedefi

Raspberry Pi 4 Model B'de AArch64 kipinde açılan bir çekirdek oluşturmak. İlk çalışan sürüm, seri konsola “Merhaba Pi 4!” yazacak. Bundan sonra bellek yönetimi, kesmeler, GPIO ve daha üst düzey özellikler eklenecek.

Bu depo şu anda başlangıç iskeletidir. Çalışan bir işletim sistemi veya derlenebilir çekirdek içerdiğini iddia etmez.

## Sabitlenen ilk kapsam

- Hedef kart: Raspberry Pi 4 Model B (Pi 4B)
- SoC: Broadcom BCM2711
- İşlemci kipi: 64-bit AArch64 / Armv8-A
- Başlangıç dili: C ve gerektiği kadar AArch64 Assembly
- İlk önyükleme hedefi: Raspberry Pi firmware'inin yüklediği kernel8.img
- İlk test: Gerçek Raspberry Pi 4B ve ayrı bir microSD kart
- Geliştirme makinesi: AArch64 bare-metal çapraz derleyicisi olan Linux/WSL ortamı

Bu depo ilk aşamada sadece Pi 4B'yi hedefler. Pi 5, Pi 3 ve başka kartlar desteklenmiş sayılmaz; destek eklemek için ayrı tasarım ve test gerekir.

## Durum

- [x] Başlangıç hedefi ve kartı belirlendi
- [ ] Derleme ortamını ve boot akışını yazılı hale getir
- [ ] AArch64 çekirdek başlangıç kodunu ekle
- [ ] kernel8.img üret
- [ ] Pi 4B'de UART üzerinden yazı göster
- [ ] GPIO LED örneği
- [ ] Kesmeler ve zamanlayıcı
- [ ] Bellek yönetimi
- [ ] Basit komut satırı

Güncel işler GitHub Issues ve geliştirme panosunda takip edilir. Ayrıntı için ROADMAP.md dosyasına bakın.

## Donanım ve önyükleme

Kart bilgileri, güç, microSD ve UART pinleri için docs/PI4B_PLATFORM.md dosyasına bakın. Önyükleme akışı ve SD kart hazırlığı docs/BOOT_AND_TEST.md içinde anlatılır.

## Katkı

Yeni katkı sahipleri good first issue etiketli görevlere bakabilir. Büyük tasarım kararlarını kodlamadan önce issue veya Discussions üzerinden konuşun. Ayrıntılar CONTRIBUTING.md dosyasında.

## Lisans

Bu başlangıç deposu MIT Lisansı ile paylaşılır. Ayrıntı LICENSE dosyasında.
