---
title: Bağlayıcı Özellikleri (Linux C++)
ms.date: 06/07/2019
ms.assetid: a0243a94-8164-425b-b2fe-b84ff363d546
ms.openlocfilehash: 934e639199d663cba391c9913b067f32e5e32165
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "79441277"
---
# <a name="linker-properties-linux-c"></a>Bağlayıcı Özellikleri (Linux C++)

::: moniker range="vs-2015"

Linux desteği Visual Studio 2017 ve sonrası sürümlerinde kullanılabilir.

::: moniker-end

::: moniker range=">=vs-2017"

## <a name="general"></a>Genel

| Özellik | Açıklama | Seçenekler |
|--|--|--|
| Çıktı Dosyası | Seçenek, bağlayıcının oluşturduğu programın varsayılan adını ve konumunu geçersiz kılar. (-o) |
| İlerlemeyi Göster | Bağlayıcı İlerleme İletilerini Yazdırır. |
| Sürüm | -sürüm seçeneği, bağlayıcıya yürütülebilir üstbilgiye bir sürüm numarası koymasını söyler. |
| Verbose Çıkışını Etkinleştir | -verbose seçeneği hata ayıklama için çıkış verbose iletileri için bağlayıcı söyler. |
| İzleme | --izleme seçeneği, bağlayıcıya işlenirken giriş dosyalarını çıktısı için söyler. |
| İz Sembolleri | Bir sembolün göründüğü dosyaların listesini yazdırın. (--iz-sembol=sembol) |
| Harita Yazdır | --print-map seçeneği, bağlayıcıya bir bağlantı eşlemi çıkarmasını söyler. |
| Çözümlenmemiş Sembol Başvurularını Bildir | Etkinleştirildiğinde bu seçenek, çözülmemiş sembol başvurularını bildirir. |
| Bellek Kullanımı için Optimize Edin | Sembol tabloları gerektiği gibi yeniden okuyarak bellek kullanımı için optimize edin. |
| Paylaşılan Kitaplık Arama Yolu | Kullanıcının paylaşılan kitaplık arama yolunu doldurmasına olanak tanır. (-rpath-link=yol) |
| Ek Kütüphane Dizinleri | Kullanıcının çevre kitaplığı yolunu geçersiz kılmasına olanak tanır. (-L klasörü). |
| Bağlayıcı | Bağlama sırasında çağırmak için program veya uzak sistemdeki bağlayıcıya giden yolu belirtir. |
| Bağlantı Zaman Dilimi | Uzaktan bağlama zaman ası, milisaniye cinsinden. |
| Çıktıyı Kopyala | Yapı çıktısı dosyasının uzak sistemden yerel makineye kopyalanıp kopyalanmayacağını belirtir. |

## <a name="input"></a>Girdi

| Özellik | Açıklama | Seçenekler |
|--|--|--|
| Belirli Varsayılan Kitaplıkları Yoksay | Varsayılan kitaplıkların bir veya daha fazla adını yoksaymak için belirtir. (--dışlama-libs lib,lib) |
| Varsayılan Kitaplıkları Yoksay | Varsayılan kitaplıkları ve yalnızca açıkça belirtilen arama kitaplıklarını yoksayın. |
| Kuvvet Tanımsız Sembol Referansları | Tanımlanmamış bir sembol olarak çıkış dosyasına girilecek kuvvet sembolü. (-u sembolü --tanımsız=sembol) |
| Kütüphane Bağımlılıkları | Bu seçenek, bağlayıcı komut satırına ek kitaplıklar eklenmesini sağlar. Ek kitaplık, 'lib' ile önceden belirlenmiş bağlayıcı komut satırının sonuna eklenir ve '.a' uzantısı ile sona erer.  (-lFILE) |
| Ek Bağımlılıklar | Bağlantı komut satırına eklenecek ek öğeler belirtir. |

## <a name="debugging"></a>Hata Ayıklama

| Özellik | Açıklama | Seçenekler |
|--|--|--|
| Hata Ayıklama Sembolü Bilgileri | Çıktı dosyasındaki hata ayıklama simgesi bilgileri. | **Tümleri Dahil Et**<br>**Omit Hata Ayıklama Sembolü Bilgi Yalnızca**<br>**Tüm Sembol Bilgilerini Atla**<br> |
| Harita Dosya Adı | Harita seçeneği, bağlayıcıya kullanıcı belirtilen adla bir harita dosyası oluşturmasını söyler. (-Harita=) |

## <a name="advanced"></a>Gelişmiş

| Özellik | Açıklama | Seçenekler |
|--|--|--|
| Değişkenleri İşaretle Yalnızca Taşınmadan Sonra Oku | Bu seçenek, yer değiştirmeden sonra salt okunur değişkenleri işaretler. |
| Anında İşlev Bağlamayı Etkinleştir | Bu seçenek, nesneyi hemen işlev bağlama için işaretler. |
| Çalıştırılabilir Yığın Gerektirmez | Bu seçenek, çıktıyı yürütülebilir yığın gerektirmeyen olarak işaretler. |
| Tüm Arşiv | Tüm Arşiv, Kaynaklar ve Ek Bağımlılıklar'dan gelen tüm kodları kullanır. |

::: moniker-end
