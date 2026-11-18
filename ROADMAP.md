# Yol haritası

Bu planın tamamlanma durumu GitHub Issues ve Project panosunda tutulur. Yol haritası bir vaat veya hazır özellik listesi değildir.

## 0. Proje temeli

- [x] Raspberry Pi 4 Model B'yi tek hedef olarak seç
- [x] 64-bit AArch64 hedefini seç
- [ ] Lisans ve bakım sorumlularını ekipçe gözden geçir
- [ ] Geliştirme ve önyükleme rehberini doğrula
- [ ] Kararları docs/DECISIONS.md dosyasında güncel tut

## 1. İlk çekirdek açılışı

- [ ] AArch64 bare-metal derleme ortamını sabitle
- [ ] Çekirdek giriş Assembly kodunu ekle
- [ ] Linker betiğini ve ikili üretimini ekle
- [ ] kernel8.img dosyasını üret
- [ ] Ayrı microSD karttan Raspberry Pi 4B'de başlat
- [ ] Seri konsola “Merhaba Pi 4!” yaz

## 2. Donanım temelleri

- [ ] Çekirdek başlarken işlemci durumunu ve çoklu çekirdek davranışını belirle
- [ ] UART sürücüsü ve hata çıktısı
- [ ] GPIO çıkış sürücüsü ve LED örneği
- [ ] Exception ve interrupt vektörleri
- [ ] Generic timer ile temel zamanlayıcı

## 3. Çekirdek özellikleri

- [ ] Device Tree bilgisini okuyup bellek haritasını keşfet
- [ ] Fiziksel bellek ayırıcı
- [ ] Sanal bellek ve MMU
- [ ] Basit görev değiştirme
- [ ] Basit kabuk/komut satırı

## 4. İleri hedefler

- [ ] SD kart ve depolama sürücüsü
- [ ] Dosya sistemi
- [ ] USB ve giriş aygıtları
- [ ] Kullanıcı modu ve sistem çağrıları
- [ ] Ağ ve grafik desteği

Bu ileri maddeler kapsam dışı bırakılabilir veya ayrı projelere bölünebilir. Her madde için önce küçük, test edilebilir issue açın.
