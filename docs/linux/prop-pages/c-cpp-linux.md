---
title: C/C++ özellikleri (Linux C++) | Microsoft Docs
ms.custom: ''
ms.date: 9/26/2017
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: Linux
ms.topic: conceptual
ms.assetid: 4bb8894b-c874-4a68-935e-b127d54e484f
author: mikeblome
ms.author: mblome
f1_keywords: []
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: 78918acc70bddb25841b2bcaaf8f7cd7b627d63b
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50061566"
---
# <a name="cc-properties-linux-c"></a>C/C++ özellikleri (Linux C++)

## <a name="general"></a>Genel

Özellik | Açıklama | Seçenekleri
--- | ---| ---
Ek içeren dizinler | Ekleme yoluna eklenecek bir veya daha fazla dizin belirtir; birden fazla ise noktalı virgülle ayırın. (-I[Path]).
Hata ayıklama bilgi biçimi | Derleyici tarafından oluşturulan hata ayıklama bilgilerinin türünü belirtir. | **Hiçbiri** -derleme daha hızlı olacak şekilde, hata ayıklama bilgisi üretir.<br/>**Minimal hata ayıklama bilgileri** -minimal hata ayıklama bilgileri oluşturur.<br/>**Tam hata ayıklama bilgileri (DWARF2)** -Oluştur DWARF2 hata ayıklama bilgileri.<br/>
Nesne dosyası adı | Varsayılan nesne dosyası adını geçersiz kılacak bir ad belirtir; Dosya veya dizin adı olabilir. (-o [ad]).
Uyarı düzeyi | Nasıl katı derleyicinin kod hataları hakkında olmasını istediğinizi seçin.  Diğer bayraklar doğrudan ek seçenekler eklenmesi gerekir. (/ w, / weverything). | **Tüm uyarıları Kapat Kapat** -tüm Derleyici uyarılarını devre dışı bırakır.<br/>**EnableAllWarnings** -varsayılan olarak devre dışı dahil olmak üzere tüm uyarıları etkinleştirir.<br/>
Uyarıları hata olarak değerlendir | Tüm Derleyici uyarılarını hata olarak değerlendirir. Yeni bir proje için tüm derlemelerde werror kullanmak en iyi olabilir. Tüm uyarıların çözümlenmesi, en az sayıda olası bulunur zor kod kusurlarını sağlayacaktır.
C için ek uyarılar | Ek uyarı iletilerinden kümesini tanımlar.
C++ için ek uyarılar | Ek uyarı iletilerinden kümesini tanımlar.
Ayrıntılı modu etkinleştir | Ayrıntılı modu etkin olduğunda, daha fazla bilgi yazdırır bu araç, yapı tanılamaya yönelik.
C derleyicisi | C kaynak dosyası ya da uzak sistemdeki C derleyicisinin yolunu derlenmesi sırasında çağrılacak programı belirtir.
C++ Derleyicisi | C++ kaynak dosyaları veya uzak sistemdeki C++ derleyicisinin yolunu derlenmesi sırasında çağrılacak programı belirtir.
Derleme zaman aşımı | Uzaktan derleme, milisaniye cinsinden zaman aşımı.
Nesne dosyalarını Kopyala | Derlenen Nesne dosyalarının Uzak sistemden yerel makineye kopyalanıp kopyalanmayacağını belirtir.

## <a name="optimization"></a>En iyi duruma getirme

Özellik | Açıklama | Seçenekleri
--- | ---| ---
En iyi duruma getirme | Uygulama için iyileştirme düzeyini belirtir. | **Özel** -özel iyileştirme.<br/>**Devre dışı bırakılmış** -iyileştirme devre dışı bırakın.<br/>**Boyutu en aza indir** -boyutu için İyileştir.<br/>**Hızı en** -hız için İyileştir.<br/>**Tam iyileştirme** -pahalı iyileştirmeler.<br/>
Katı örtüşme | En katı örtüşme kurallarını varsayın.  Bir türde bir nesne hiçbir zaman farklı türde bir nesne olarak aynı adreste bulunan olduğu kabul edilir.
Döngüleri Aç | Daha büyük kod boyutu malitetiyle yürütülen dal sayısını azaltarak uygulamayı daha hızlı hale getirmek için döngüleri açın.
Bağlantı süresi iyileştirmesi | İyileştirici uygulamanızdaki nesne dosyaları arasında görünmesini izin vererek arası yordam povoluje optimalizace.
Çerçeve işaretçisini atlama | Çağrı yığınında çerçeve işaretçilerinin oluşturulmasını engeller.
Ortak blok yok | Yerine bunları ortak bloklar olarak oluşturmak nesne dosyasının veri bölümündeki başlatılmamış genel değişkenleri Ayır

## <a name="preprocessor"></a>Ön işlemci

Özellik | Açıklama | Seçenekleri
--- | ---| ---
Önişlemci tanımları | Kaynak dosyanız için ön işleme sembollerini tanımlar. (-D)
Ön İşlemci tanımlarını Kaldır | Bir veya daha çok önişlemci tanımsızı belirtir.  (-U [macro])
Tüm önişlemci tanımlarını Kaldır | Önceden tanımlanmış tüm önişlemci değerlerini Kaldır.  (-undef)
Ekleme kodlarını Göster | Derleyici çıkışıyla ekleme kodu dosyalarının bir listesini oluşturur.  (-H)

## <a name="code-generation"></a>Kod Üretimi

Özellik | Açıklama | Seçenekleri
--- | ---| ---
Konumdan bağımsız kod | Paylaşılan bir kitaplık kullanmak için konum bağımsız kod (PIC) oluştur.
İş parçacığı güvenli Statikleri olan | İş parçacığı güvenli olarak başlatılması amacıyla yerel statiklerin için C++ ABI'SİNDE belirtilen yordamları kullanmak için ek kod gösterir. | **Hayır** -iş parçacığı güvenli statik başlatmaları devre dışı bırakın.<br/>**Evet** -iş parçacığı güvenli Statikleri etkinleştirin.<br/>
Kayan nokta iyileştirme | Nokta iyileştirmelerini sakin IEEE-754 uyumluluğunu esnekleştirerek kayan etkinleştirir.
Satır içi yöntemler gizli | Etkinleştirildiğinde, satır içi yöntemlerin satır dışı kopyaları 'özel dış' olarak bildirilir.
Sembol varsayılan olarak gizli | Tüm semboller, '__attribute' makrosu kullanılarak dışarı aktarılmak için açıkça işaretlenmiş sürece 'özel dış' bildirilir.
C++ özel durumlarını etkinleştir | Derleyici tarafından kullanılması için özel durum işleme modelini belirtir. | **Hayır** -özel durum işleme devre dışı bırakın.<br/>**Evet** -özel durum işlemeyi etkinleştirin.<br/>

## <a name="language"></a>Dil

Özellik | Açıklama | Seçenekleri
--- | ---| ---
Çalışma zamanı tür bilgisini etkinleştir | Çalışma zamanında (çalışma zamanı tür bilgisi) C++ nesne türlerini denetlemek için kod ekler.     (frtti, fno-rtti)
C dil standardı | C dil standardını belirler. | **Default**<br/>**C89** -C89 dil standardı.<br/>**C99** -C99 dil standardı.<br/>**C11** -C11 dil standardı.<br/>**C99 (GNU diyalekti)** -C99 (GNU diyalekti) dil standardı.<br/>**C11 (GNU diyalekti)** -C11 (GNU diyalekti) dil standardı.<br/>
C++ dil standardı | C++ dil standardını belirler. | **Default**<br/>**C ++ 03** -C ++ 03 dil standardı.<br/>**C ++ 11** -C ++ 11 dil standardı.<br/>**C ++ 14** -C ++ 14 dil standardı.<br/>**C ++ 03 (GNU diyalekti)** - C ++ 03 (GNU diyalekti) dil standardı.<br/>**C ++ 11 (GNU diyalekti)** - C ++ 11 (GNU diyalekti) dil standardı.<br/>**C ++ 14 (GNU diyalekti)** - C ++ 14 (GNU diyalekti) dil standardı.<br/>

## <a name="advanced"></a>Gelişmiş

Özellik | Açıklama | Seçenekleri
--- | ---| ---
Olarak derleme | .C ve .cpp dosyaları için derleme dili tercihini seçin.  'Default' göre .c veya .cpp uzantı algılar. (-x c, -x c++) | **Varsayılan** -varsayılan.<br/>**C kodu olarak derle** -C kodu olarak derle.<br/>**C++ kodu olarak derle** -C++ kodu olarak derle.<br/>
Zorlanmış dosyaları Ekle | Bir veya daha fazla zorunlu ekleme dosyaları (-include [ad])

## <a name="additional-options"></a>Ek Seçenekler
