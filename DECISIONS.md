# Teknik kararlar

## Kabul edilen kararlar

| Konu | Karar |
| --- | --- |
| İlk ve tek kart hedefi | Raspberry Pi 4 Model B |
| SoC | Broadcom BCM2711 |
| CPU hedefi | 64-bit AArch64 / Armv8-A |
| İlk kernel dosya adı | kernel8.img |
| İlk diller | C ve gereken kadar AArch64 Assembly |
| İlk test | Gerçek Pi 4B, ayrı microSD kart |
| Başlangıç lisansı | MIT |

## Karar bekleyen konular

- Bare-metal toolchain sürümü ve kurulum adımları
- Firmware'in kernel'e verdiği başlangıç adresi ve CPU exception level varsayımları
- Başlangıçta kaç çekirdeğin çalıştırılacağı; ikincil çekirdeklerin park edilme yöntemi
- UART0 PL011 mi, UART1 mini UART mı kullanılacak?
- Device Tree'nin ilk aşamada nasıl okunacağı
- RAM haritası, linker yerleşimi, stack boyutları ve framebuffer hedefi
- SD kartın imaj/partition düzeni

Bir karar değişirse tabloyu ve etkilenmiş dokümanları aynı Pull Request'te güncelleyin.
