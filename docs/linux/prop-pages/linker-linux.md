---
title: Bağlayıcı özellikleri (Linux C++)
ms.date: 9/26/2017
ms.assetid: a0243a94-8164-425b-b2fe-b84ff363d546
ms.openlocfilehash: db2fc37189ca05835888faed26b242abc0fe5fcb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50580680"
---
# <a name="linker-properties-linux-c"></a>Bağlayıcı özellikleri (Linux C++)

## <a name="general"></a>Genel

Özellik | Açıklama | Seçenekleri
--- | ---| ---
Çıkış dosyası | Seçeneği, varsayılan adı ve bağlayıcının oluşturduğu program konumunu geçersiz kılar. (-o).
İlerlemeyi Göster | Bağlayıcı ilerleme iletilerini yazdırır.
Sürüm | -Version seçeneği bağlayıcıya yürütülebilir dosya üst bilgisinde sürüm numarası yerleştirin.
Ayrıntılı çıkışı etkinleştir | Verbose seçeneği, sistemi, hata ayıklama için ayrıntılı iletiler çıkarmasını söyler.
İzleme | --Trace seçeneği bağlayıcıya, giriş dosyaları işlendikçe çıkışlarını söyler.
Sembolleri İzle | İçinde Sembol görüntülenen dosyaların listesini yazdırma. (--trace-symbol = symbol)
Eşlemi Yazdır | Print-map seçeneği bağlayıcıya bir bağlantı eşlemesi çıkışı.
Çözümlenmeyen sembol başvurularını bildir | Bu seçenek etkinleştirildiğinde, çözümlenmeyen sembol başvurularını bildirir.
Bellek kullanımı için İyileştir | Gerekirse sembol tablolarını yeniden okuyarak bellek kullanımı için İyileştir.
Paylaşılan kitaplık arama yolu | Kullanıcının paylaşılan kitaplık arama yolunu doldurmasına izin verir. (- rpath - bağlantı = path)
Ek Kitaplık dizinleri | Kullanıcının ortam kitaplık yolunu geçersiz kılmasına izin verir. (-L klasör).
Bağlayıcı | Bağlama ya da uzak sistemdeki bağlayıcının yolunu sırasında çağrılacak programı belirtir.
Bağlantı zaman aşımı | Uzaktan bağlama milisaniye cinsinden zaman aşımı.
Çıkışı Kopyala | Derleme çıkışı dosyasının Uzak sistemden yerel makineye kopyalanıp kopyalanmayacağını belirtir.

## <a name="input"></a>Giriş

Özellik | Açıklama | Seçenekleri
--- | ---| ---
Varsayılan özel kitaplıkları yoksay | Bir veya daha fazla varsayılan kitaplık adlarını belirtir. (--exclude-libs lib, lib)
Varsayılan kitaplıkları yoksay | Varsayılan kitaplıkları yoksayar ve yalnızca açıkça belirtilen kitaplıklarda arar.
Tanımsız sembol başvurularını zorla | Çıkış dosyasına tanımsız bir sembol olarak girilmeye zorla. (- u symbol--undefined = symbol)
Kitaplık bağımlılıkları | Bu seçenek, özel olarak bağlayıcı komut satırına eklenecek ek kitaplıklar belirtmeye izin verir. Ek Kitaplık, 'lib' ve '.a' uzantısıyla bitiş ön eki bağlayıcı komut satırının sonuna eklenir.  (-Lfıle)
{1&gt;Ek Bağımlılıklar&lt;1} | Bağlama komut satırına eklenecek ek öğeleri belirtir.

## <a name="debugging"></a>Hata Ayıklama

Özellik | Açıklama | Seçenekleri
--- | ---| ---
Hata ayıklayıcı sembol bilgisi | Hata ayıklayıcı sembol bilgisi çıkış dosyasından'nı tıklatın. | **Tüm ekleme**<br>**Yalnızca hata ayıklayıcı sembol bilgilerini çıkar**<br>**Tüm sembol bilgilerini çıkar**<br>
Eşlem dosyası adı | Map seçeneği bağlayıcıya belirtilen kullanıcı adıyla bir eşleme dosyası oluşturmasını söyler. (-Map =)

## <a name="advanced"></a>Gelişmiş

Özellik | Açıklama | Seçenekleri
--- | ---| ---
Yeniden konumlandırmadan sonra değişkenleri ReadOnly işaretle | Bu seçenek, yeniden konumlandırmadan sonra değişkenleri salt okunur işaretler.
İşlevi hemen bağlamayı etkinleştir | Bu seçenek, nesne işlevi hemen bağlama için işaretler.
Yürütülebilir yığın gerektirme | Bu seçenek, çıkışı, yürütülebilir yığını gerektirmiyor olarak işaretler.
Tüm arşiv | Tüm Arşiv, kaynaklar ve ek bağımlılıklar'daki tüm kodu kullanır.
