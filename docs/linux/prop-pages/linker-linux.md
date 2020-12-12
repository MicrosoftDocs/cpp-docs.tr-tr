---
description: 'Daha fazla bilgi edinin: bağlayıcı Özellikleri (Linux C++)'
title: Bağlayıcı Özellikleri (Linux C++)
ms.date: 06/07/2019
ms.assetid: a0243a94-8164-425b-b2fe-b84ff363d546
ms.openlocfilehash: 93ded9016cecb629fe17d171387260179b208f77
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97169755"
---
# <a name="linker-properties-linux-c"></a>Bağlayıcı Özellikleri (Linux C++)

::: moniker range="msvc-140"

Linux desteği, Visual Studio 2017 ve üzeri sürümlerde kullanılabilir.

::: moniker-end

::: moniker range=">=msvc-150"

## <a name="general"></a>Genel

| Özellik | Açıklama | Seçenekler |
|--|--|--|
| Çıkış dosyası | Seçeneği, bağlayıcının oluşturduğu programın varsayılan adını ve konumunu geçersiz kılar. (-o) |
| Ilerlemeyi göster | Bağlayıcı Ilerleme Iletilerini yazdırır. |
| Sürüm | -Version seçeneği, bağlayıcıya yürütülebilir dosyanın üstbilgisine bir sürüm numarası koymasını söyler. |
| Ayrıntılı çıktıyı etkinleştir | -Verbose seçeneği, bağlayıcıya hata ayıklama için ayrıntılı iletiler çıkışını söyler. |
| İzleme | --Trace seçeneği, bağlayıcının girdi dosyalarını işlenmiş olarak çıktısını vermesini söyler. |
| İzleme sembolleri | Bir simgenin göründüğü dosyaların listesini yazdırın. (--trace-symbol = Symbol) |
| Harita Yazdır | --Print-MAP seçeneği, bağlayıcının bir bağlantı eşlemesi çıkışı oluşturmasını söyler. |
| Çözümlenmemiş sembol başvurularını raporla | Etkin olduğunda bu seçenek çözümlenmemiş sembol başvurularını rapor eder. |
| Bellek kullanımı Için iyileştirin | Bellek kullanımı için okuyarak, sembol tablolarını gereken şekilde iyileştirin. |
| Paylaşılan kitaplık arama yolu | Kullanıcının paylaşılan kitaplık arama yolunu doldurmasına izin verir. (-Rpath-Link = yol) |
| Ek kitaplık dizinleri | Kullanıcının ortam kitaplık yolunu geçersiz kılmasına izin verir. (-L klasörü). |
| Bağlayıcı | Bağlama sırasında çağrılacak programı veya uzak sistemdeki bağlayıcının yolunu belirtir. |
| Bağlantı zaman aşımı | Milisaniye cinsinden uzaktan bağlama zaman aşımı. |
| Çıkışı Kopyala | Derleme çıkış dosyasının uzak sistemden yerel makineye kopyalanıp kopyalanmayacağını belirtir. |

## <a name="input"></a>Giriş

| Özellik | Açıklama | Seçenekler |
|--|--|--|
| Belirli varsayılan kitaplıkları Yoksay | Yoksayılacak bir veya daha fazla varsayılan kitaplık adını belirtir. (--exclude-libs lib, lib) |
| Varsayılan kitaplıkları Yoksay | Varsayılan kitaplıkları Yoksay ve yalnızca açık olarak belirtilen kitaplıkları ara. |
| Tanımsız sembol başvurularını zorla | Simgenin çıkış dosyasına tanımsız bir sembol olarak girilmesini zorla. (-u symbol--tanımsız = simge) |
| Kitaplık bağımlılıkları | Bu seçenek bağlayıcı komut satırına eklenecek ek kitaplıkların belirtilmesine izin verir. Ek kitaplık, ' lib ' önekini önekli ve '. a ' uzantısıyla biten bağlayıcı komut satırının sonuna eklenir.  (-lFILE) |
| Ek bağımlılıklar | Bağlantı komut satırına eklenecek ek öğeleri belirtir. |

## <a name="debugging"></a>Hata Ayıklama

| Özellik | Açıklama | Seçenekler |
|--|--|--|
| Hata ayıklayıcı sembol bilgisi | Çıkış dosyasından hata ayıklayıcı sembol bilgisi. | **Tümünü dahil et**<br>**Yalnızca hata ayıklayıcı sembol bilgisini atla**<br>**Tüm sembol bilgilerini atla**<br> |
| Eşleme dosyası adı | MAP seçeneği, bağlayıcının Kullanıcı tanımlı ada sahip bir eşleme dosyası oluşturmasını söyler. (-Map =) |

## <a name="advanced"></a>Gelişmiş

| Özellik | Açıklama | Seçenekler |
|--|--|--|
| Yeniden konumlandırmadan sonra değişkenleri ReadOnly olarak işaretle | Bu seçenek, yeniden konumlandırmadan sonra değişkenleri salt okunurdur. |
| Hemen Işlev bağlamayı etkinleştir | Bu seçenek, hemen işlev bağlamasının nesnesini işaretler. |
| Yürütülebilir yığın gerektirme | Bu seçenek çıktıyı yürütülebilir yığın gerektirmeyen olarak işaretler. |
| Tüm arşiv | Tüm arşiv kaynaklardaki tüm kodu ve ek bağımlılıkları kullanır. |

::: moniker-end
