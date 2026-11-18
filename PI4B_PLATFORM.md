# Raspberry Pi 4B platform rehberi

## Kart ve işlemci

Raspberry Pi 4 Model B, Broadcom BCM2711 SoC ve dört çekirdekli 64-bit Cortex-A72 işlemci kullanır. Bu proje yalnızca 64-bit AArch64 / Armv8-A kipini hedefler. Pi 4B kartları farklı RAM miktarlarıyla satıldığı için RAM miktarını sabit kabul etmeyin; bellek haritasını firmware'in sağladığı Device Tree bilgisinden öğrenmek sonraki aşamanın işidir.

## Gerekli donanım

- Raspberry Pi 4 Model B
- Deneme sistemi için ayırabileceğiniz microSD kart
- Kaliteli 5V/3A USB-C güç kaynağı
- İlk açılış için micro-HDMI kablosu ve ekran
- Klavye (daha sonra çekirdek USB desteği geldiğinde kullanılabilir)
- UART debug için opsiyonel 3.3V USB-serial adaptör

Pi 4B için üretici önerisi 5V/3A USB-C güç kaynağıdır. İlk denemeleri günlük kullandığınız SD kart yerine ayrı kartla yapın; özel kernel boot etmeyebilir ve normal işletim sistemi açılmaz.

## Boot dosyası ve 64-bit hedef

Raspberry Pi firmware'i boot bölümündeki config.txt dosyasını Arm işlemcisi başlamadan önce okur. Raspberry Pi belgelerinde kernel8.img, BCM2711 üzerinde 64-bit kernel adı olarak listelenir. Bu depodaki ilk bare-metal imajının da bu isimle üretilmesi planlanıyor.

Firmware, kart modeline göre Device Tree blob (DTB) dosyasını da yükleyebilir. Çekirdek bellek ve aygıt bilgilerini bu veriden okumalı; Pi 4B'deki RAM ve çevrebirim adreslerini başka Raspberry Pi modellerinin adresleriyle karıştırmamalıdır.

## UART ve GPIO

Pi 4'te GPIO14 (40-pin başlığın fiziksel pin 8'i) UART TX, GPIO15 (fiziksel pin 10) UART RX olarak kullanılabilir. Pi 4'te UART0 PL011, UART1 ise mini UART'tır; varsayılan ana UART yönlendirmesinde Bluetooth ve seri pinlerin eşleşmesini kontrol etmek gerekir. Önce hangi UART'ın kullanılacağı kararlaştırılmadan sürücüye sabit adres yazmayın.

GPIO/UART sinyalleri 3.3V seviyesindedir. USB-serial adaptörde yalnızca uygun 3.3V TTL seviyesini kullanın; 5V sinyal Pi'ye zarar verebilir. UART bağlantısında genellikle GND, Pi TX → adaptör RX ve Pi RX → adaptör TX bağlanır. Adaptörün 5V/VCC hattını Pi GPIO'ya bağlamayın.

## Resmi kaynaklar

- [Raspberry Pi 4B ürün özellikleri](https://www.raspberrypi.com/products/raspberry-pi-4-model-b/specifications/)
- [Raspberry Pi boot yapılandırması ve kernel dosya adları](https://www.raspberrypi.com/documentation/computers/configuration.html)
- [config.txt rehberi](https://www.raspberrypi.com/documentation/computers/config_txt.html)
- [UART ve GPIO seri bağlantısı](https://www.raspberrypi.com/documentation/computers/configuration.html)
- [BCM2711 çevrebirim veri sayfası (PDF)](https://pip-assets.raspberrypi.com/categories/545-raspberry-pi-4-model-b/documents/RP-008248-DS-1-bcm2711-peripherals.pdf)
