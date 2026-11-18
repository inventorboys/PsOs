# Pi 4B'de boot ve ilk test planı

Bu dosya ilk denemeyi nasıl yapacağınızı anlatır. Depoda henüz derlenebilir bir kernel bulunmadığı için bugün çalıştırabileceğiniz kernel8.img de yoktur. Kernel issue'ları tamamlandığında aşağıdaki akış kullanılacaktır.

## 1. Geliştirme kartını hazırla

1. Raspberry Pi 4B için ayrı bir microSD kart ayırın.
2. Raspberry Pi Imager ile Raspberry Pi OS Lite 64-bit yazın. Bu, ilk denemede firmware/boot dosyalarını hazır bulundurmanın kolay yoludur.
3. Kartı bilgisayara takın ve boot bölümündeki config.txt dosyasını açın.
4. Var olan dosyanın tamamını silmeyin. arm_64bit veya kernel ayarı zaten varsa aynı satırı tekrar eklemek yerine değerini düzenleyin; yoksa dosyanın sonuna ekleyin:

    arm_64bit=1
    kernel=kernel8.img

arm_64bit ve kernel firmware ayarlarıdır. Boot bölümüne projenin derlenmiş kernel8.img dosyası kopyalanınca firmware onu yüklemeyi dener.

## 2. İlk kernel hazır olduğunda

1. Projedeki kurulum rehberine göre AArch64 bare-metal çapraz derleyicisini kurun.
2. README'de sonradan ilan edilecek build komutuyla kernel imajını üretin.
3. Derlenen kernel8.img dosyasını SD kartın boot bölümüne kopyalayın.
4. Kartı güvenli biçimde çıkarıp Pi 4B'ye takın.
5. HDMI ekranı ve güç kaynağını bağlayıp açın.
6. Ekran veya UART çıktısında beklenen mesajı gözleyin. İlk sürümde HDMI grafik ekranı hedef değildir; UART çıktısı tercih edilir.

## 3. UART ile debug

UART kullanacaksanız önce docs/PI4B_PLATFORM.md içindeki Pi 4 pin ve UART yönlendirme notlarını okuyun. enable_uart=1 ayarı firmware/Linux seri konsolu için kullanışlı olabilir; çıplak-metal sürücü hangi UART'ı kullanacağını ayrıca belirlemelidir. Pi 4'te UART0 ve UART1 rollerini varsayımla karıştırmayın.

İlk denemelerde seri kablo olmadan HDMI üzerinden boot belirtisini kontrol edin. UART adaptörünüz varsa 3.3V TTL uyumlu olduğundan emin olun.

## 4. Boot başarısız olursa

- Pi'nin normalde açılabildiği ayrı bir SD kartı saklayın.
- Test kartındaki config.txt değişikliğini geri alın veya Raspberry Pi OS imajını yeniden yazın.
- Sorun issue'suna Pi modeli, RAM miktarı, boot dosyalarının listesi, config.txt ve gözlenen LED/ekran/UART davranışını ekleyin.
- SD kartın boot bölümünde kernel imajının tam adının kernel8.img olduğunu kontrol edin.

## 5. Şu an neden build komutu yok?

Başlangıç paketi repo ve proje yönetimini hazırlar. Kernel girişi, linker adresi, firmware'in bıraktığı işlemci durumu ve UART seçimi kararlaştırılıp gerçek Pi 4B'de denenmeden çalışmayan bir build komutu koymak yanıltıcı olur. Bu kararlar ROADMAP'teki ilk çekirdek aşamasında eklenecektir.
