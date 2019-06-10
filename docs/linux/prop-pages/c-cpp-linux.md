---
title: C/C++ özellikleri (Linux C++)
ms.date: 06/07/2019
ms.assetid: 4bb8894b-c874-4a68-935e-b127d54e484f
f1_keywords: []
ms.openlocfilehash: b5be7582970c45e25f1e2c90971d587c19eac2a0
ms.sourcegitcommit: 8adabe177d557c74566c13145196c11cef5d10d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/10/2019
ms.locfileid: "66821338"
---
# <a name="cc-properties-linux-c"></a>C/C++ özellikleri (Linux C++)

::: moniker range="vs-2015"

Linux desteği, Visual Studio 2017 ile kullanılabilir ve üzerinde desteklenir.

::: moniker-end

::: moniker range=">=vs-2017"

## <a name="general"></a>Genel

Özellik | Açıklama | Seçenekleri
--- | ---| ---
Ek içeren dizinler | Ekleme yoluna eklenecek bir veya daha fazla dizin belirtir. Birden çok dizini ayırmak için noktalı virgül kullanın. (-I\[yolu]).
Hata ayıklama bilgi biçimi | Derleyici tarafından oluşturulan hata ayıklama bilgilerinin türünü belirtir. | **Hiçbiri** -derleme daha hızlı olacak şekilde, hata ayıklama bilgisi üretir.<br/>**Minimal hata ayıklama bilgileri** -minimal hata ayıklama bilgileri oluşturur.<br/>**Tam hata ayıklama bilgileri (DWARF2)** -Oluştur DWARF2 hata ayıklama bilgileri.<br/>
Nesne dosyası adı | Varsayılan nesne dosyası adını geçersiz kılacak bir ad belirtir. Bu dosya veya dizin adı olabilir. (-o [ad]).
Uyarı düzeyi | Derleyicinin kod hataları hakkında olmasını istediğiniz nasıl katı seçer.  Diğer bayraklar doğrudan ekleme **ek seçenekler**. (/ w, / weverything). | **Tüm uyarıları Kapat Kapat** -tüm Derleyici uyarılarını devre dışı bırakır.<br/>**EnableAllWarnings** -varsayılan olarak devre dışı olanları dahil olmak üzere tüm uyarıları etkinleştirir.<br/>
Uyarıları hata olarak değerlendir | Tüm Derleyici uyarılarını hata olarak değerlendirir. Yeni bir proje için tüm derlemelerde werror kullanmak en iyi olabilir. En az sayıda olası bulunur zor kod kusurlarını emin olmak için tüm uyarıları çözümleyin.
C için ek uyarılar | Ek uyarı iletilerinden kümesini tanımlar.
C++ için ek uyarılar | Ek uyarı iletilerinden kümesini tanımlar.
Ayrıntılı modu etkinleştir | Ayrıntılı modu etkin olduğunda, derleme tanılamak için daha fazla bilgi yazdırır.
C derleyicisi | C kaynak dosyası ya da uzak sistemdeki C derleyicisinin yolunu derlenmesi sırasında çağrılacak programı belirtir.
C++ Derleyicisi | C++ kaynak dosyaları veya uzak sistemdeki C++ derleyicisinin yolunu derlenmesi sırasında çağrılacak programı belirtir.
Derleme zaman aşımı | Uzaktan derleme, milisaniye cinsinden zaman aşımı.
Nesne dosyalarını Kopyala | Derlenen Nesne dosyalarının Uzak sistemden yerel makineye kopyalanıp kopyalanmayacağını belirtir.

## <a name="optimization"></a>İyileştirme

Özellik | Açıklama | Seçenekleri
--- | ---| ---
İyileştirme | Uygulama için iyileştirme düzeyini belirtir. | **Özel** -özel iyileştirme.<br/>**Devre dışı bırakılmış** -iyileştirme devre dışı bırakın.<br/>**Boyutu en aza indir** -boyutu için İyileştir.<br/>**Hızı en** -hız için İyileştir.<br/>**Tam iyileştirme** -pahalı iyileştirmeler.
Katı örtüşme | En katı örtüşme kurallarını varsayar.  Bir türde bir nesne hiçbir zaman farklı türde bir nesne aynı adresi olduğu varsayılır.
Döngüleri Aç | Daha büyük kod boyutu malitetiyle yürütülen dal sayısını azaltarak uygulamayı daha hızlı hale getirmek için döngüleri unrolls.
Bağlantı süresi iyileştirmesi | İyileştirici uygulamanızdaki nesne dosyaları arasında görünmesini izin vererek arası yordam iyileştirmeler sağlar.
Çerçeve işaretçisini atlama | Çağrı yığınında çerçeve işaretçilerinin oluşturulmasını engeller.
Ortak blok yok | Onları ortak bloklar olarak oluşturmak yerine nesne dosyasının veri bölümündeki bile başlatılmamış genel değişkenleri ayırır.

## <a name="preprocessor"></a>Ön işlemci

Özellik | Açıklama | Seçenekleri
--- | ---| ---
Önişlemci tanımları | Kaynak dosyanız için ön işleme sembollerini tanımlar. (-D)
Ön İşlemci tanımlarını Kaldır | Bir veya daha çok önişlemci tanımsızı belirtir.  (-U \[makrosu])
Tüm önişlemci tanımlarını Kaldır | Önceden tanımlanmış tüm önişlemci değerlerini tanımsızı.  (-undef)
Ekleme kodlarını Göster | Derleyici çıkışıyla ekleme kodu dosyalarının bir listesini oluşturur.  (-H)

## <a name="code-generation"></a>Kod Üretimi

Özellik | Açıklama | Seçenekleri
--- | ---| ---
Konumdan bağımsız kod | Paylaşılan bir kitaplık kullanmak için konumu-bağımsız kod (PIC) oluşturur.
İş parçacığı güvenli Statikleri olan | Belirtilen yordamları kullanmak için ek bir kod yayan C++ ABI yerel statiklerin iş parçacığı açısından güvenli başlatma. | **Hayır** -iş parçacığı güvenli Statikleri devre dışı bırakın.<br/>**Evet** -iş parçacığı güvenli Statikleri etkinleştirin.
Kayan nokta iyileştirme | Sakin IEEE-754 uyumluluğunu esnekleştirerek kayan nokta iyileştirmelerini etkinleştirir.
Satır içi yöntemler gizli | Etkinleştirildiğinde, satır içi yöntemlerin satır dışı kopyaları bildirilen `private extern`.
Varsayılan olarak Gizli simgeleri | Tüm semboller bildirilen `private extern` açıkça kullanarak dışarı aktarmak için işaretlenmiş sürece `__attribute` makrosu.
C++ özel durumlarını etkinleştir | Derleyici tarafından kullanılan özel durum işleme modelini belirtir. | **Hayır** -özel durum işleme devre dışı bırakın.<br/>**Evet** -özel durum işlemeyi etkinleştirin.

## <a name="language"></a>Dil

Özellik | Açıklama | Seçenekleri
--- | ---| ---
Çalışma zamanı tür bilgisini etkinleştir | Çalışma zamanında (çalışma zamanı tür bilgisi) C++ nesne türlerini denetlemek için kod ekler.     (frtti, fno-rtti)
C dil standardı | C dil standardını belirler. | **Default**<br/>**C89** -C89 dil standardı.<br/>**C99** -C99 dil standardı.<br/>**C11** -C11 dil standardı.<br/>**C99 (GNU diyalekti)** -C99 (GNU diyalekti) dil standardı.<br/>**C11 (GNU diyalekti)** -C11 (GNU diyalekti) dil standardı.
C++ dil standardı | C++ dil standardını belirler. | **Default**<br/>**C ++ 03** -C ++ 03 dil standardı.<br/>**C ++ 11** -C ++ 11 dil standardı.<br/>**C ++ 14** -C ++ 14 dil standardı.<br/>**C ++ 03 (GNU diyalekti)** - C ++ 03 (GNU diyalekti) dil standardı.<br/>**C ++ 11 (GNU diyalekti)** - C ++ 11 (GNU diyalekti) dil standardı.<br/>**C ++ 14 (GNU diyalekti)** - C ++ 14 (GNU diyalekti) dil standardı.

## <a name="advanced"></a>Gelişmiş

Özellik | Açıklama | Seçenekleri
--- | ---| ---
Olarak derleme | .C ve .cpp dosyaları için derleme dil seçeneğini seçer. (-x c, -x c++) | **Varsayılan** -algılamak .c veya .cpp uzantısına göre.<br/>**C kodu olarak derle** -C kodu olarak derle.<br/>**Olarak derlenmesine C++ kod** -olarak derlenmesine C++ kod.
Zorlanmış dosyaları Ekle | Bir veya daha fazla zorunlu ekleme dosyaları belirtir. (-dahil \[adı])

::: moniker-end
