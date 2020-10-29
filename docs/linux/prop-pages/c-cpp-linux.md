---
title: C/C++ özellikleri (Linux C++)
ms.date: 10/14/2020
description: Visual Studio C/C++ özellikleri sayfasında Linux derleme seçeneklerini açıklar
ms.assetid: 4bb8894b-c874-4a68-935e-b127d54e484f
f1_keywords: []
ms.openlocfilehash: b8cb1d8c6c585262e966c3015660adeaeab60307
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92924563"
---
# <a name="cc-properties-linux-c"></a>C/C++ özellikleri (Linux C++)

::: moniker range="msvc-140"

Linux desteği, Visual Studio 2017 ve üzeri sürümlerde kullanılabilir.

::: moniker-end

::: moniker range=">=msvc-150"

## <a name="general"></a>Genel

| Özellik | Açıklama | Seçenekler |
|--|--|--|
| Ek Içerme dizinleri | Ekleme yoluna eklenecek bir veya daha fazla dizini belirtir. Birden çok dizini ayırmak için noktalı virgül kullanın. (-I \[ yolu]). |
| Hata ayıklama bilgi biçimi | Derleyici tarafından oluşturulan hata ayıklama bilgilerinin türünü belirtir. | **Hiçbiri** -hata ayıklama bilgisi üretmez, bu nedenle derleme daha hızlı olabilir.<br/>**Minimal hata ayıklama bilgileri** -en düşük hata ayıklama bilgileri oluştur.<br/>**Tam hata ayıklama bilgileri (DWARF2)** -DWARF2 hata ayıklama bilgileri oluştur.<br/> |
| Nesne dosyası adı | Varsayılan nesne dosyası adını geçersiz kılacak bir ad belirtir. Bu bir dosya veya dizin adı olabilir. (-o [ad]). |
| Uyarı düzeyi | Derleyicinin kod hataları hakkında ne kadar sıkı olmasını istediğinizi seçer.  Diğer bayrakları doğrudan **ek seçeneklere** ekleyin. (/w,/Weverything). | **Tüm uyarıları** kapat-tüm derleyici uyarılarını devre dışı bırakır.<br/>**Enablealluyarılar** -varsayılan olarak devre dışı bırakılmış olanlar da dahil olmak üzere tüm uyarıları etkinleştirilir.<br/> |
| Uyarıları hata olarak değerlendir | Tüm derleyici uyarılarını hata olarak değerlendirir. Yeni bir proje için tüm derlemelerde/Werror kullanılması en iyi yöntem olabilir. En az olası kod kusurlarını sağlamak için tüm uyarıları çözün. |
| C ek uyarılar | Ek bir uyarı iletileri kümesi tanımlar. |
| C++ ek uyarıları | Ek bir uyarı iletileri kümesi tanımlar. |
| Ayrıntılı modu etkinleştir | Ayrıntılı mod etkinleştirildiğinde, derlemeyi tanılamak için daha fazla bilgi yazdırır. |
| C derleyicisi | C kaynak dosyalarının derlenmesi sırasında çağrılacak programı veya uzak sistemdeki C derleyicisinin yolunu belirtir. |
| C++ Derleyicisi | C++ kaynak dosyalarının derlenmesi sırasında çağrılacak programı veya uzak sistemdeki C++ derleyicisinin yolunu belirtir. |
| Derleme zaman aşımı | Uzak derleme zaman aşımı, milisaniye cinsinden. |
| Nesne dosyalarını Kopyala | Derlenen nesne dosyalarının, uzak sistemden yerel makineye kopyalanıp kopyalanmayacağını belirtir. |
| En fazla paralel derleme Işleri | Derleme sırasında paralel olarak oluşturulacak işlem sayısı. Varsayılan değer 1'dir. Linux için Windows alt sistemi (WSL) sürüm 1 kullanıyorsanız, sınır 64 ' dir. |
| Mimariyi Doğrula | Projenin hedeflediği platformun uzak sistemle eşleşip eşleşmediğini denetleyip denetmeyeceğinizi belirtin.|
| Adres Temizleme özelliğini etkinleştir | Çalışma zamanı belleği sorunlarını bulma ve Aralık dışı denetimleri gerçekleştirme hızlı bir bellek hata algılayıcısı olan, programı adres Temizleme ile derleyin.|

## <a name="optimization"></a>İyileştirme

| Özellik | Açıklama | Seçenekler |
|--|--|--|
| İyileştirme | Uygulamanın en iyi duruma getirme düzeyini belirtir. | **Özel** -özel iyileştirme.<br/>**Devre dışı** -iyileştirmeyi devre dışı bırak.<br/>**Boyutu en aza indirir** -boyut için iyileştirin.<br/>**En yüksek hız** -hız için iyileştirin.<br/>**Tam iyileştirme** maliyetli iyileştirmeler. |
| Katı diğer ad | En katı diğer ad kurallarını varsayar.  Tek bir türdeki nesne, farklı türde bir nesneyle aynı adrese sahip olacak şekilde hiçbir şekilde kabul değildir. |
| Döngüleri geri alma | Daha büyük kod boyutu maliyetinde yürütülen dalların sayısını azaltarak uygulamayı daha hızlı hale getirmek için yapılan döngüleri kaldırır. |
| Bağlantı süresi Iyileştirmesi | İyileştiricinin uygulamanızdaki nesne dosyalarına bakmalarına izin vererek yordamsal iyileştirmeleri sağlar. |
| Çerçeve Işaretçisini atla | Çağrı yığınında çerçeve işaretçilerinin oluşturulmasını engeller. |
| Ortak blok yok | Ortak bloklar olarak oluşturmak yerine, nesne dosyasının veri bölümünde bile başlatılmamış genel değişkenler ayırır. |

## <a name="preprocessor"></a>Ön işlemci

| Özellik | Açıklama |
|--|--|
| Önişlemci tanımları | Kaynak dosyanız için ön işleme sembollerini tanımlar. (-D) |
| Önişlemci tanımlarının tanımı kaldırılıyor | Bir veya daha fazla önişlemci tarafından tanımlanabileceğini belirtir.  (-U \[ makrosu]) |
| Tüm önişlemci tanımlarının tanımlanunlarını kaldır | Önceden tanımlanmış tüm Önişlemci değerlerini tanımlar.  (-undef) |
| Eklemeleri göster | Derleyici çıkışı içeren ekleme dosyalarının bir listesini oluşturur.  (-H) |

## <a name="code-generation"></a>Kod Üretimi

| Özellik | Açıklama | Seçenekler |
|--|--|--|
| Konumdan bağımsız kod | Paylaşılan bir kitaplıkta kullanılmak üzere konumdan bağımsız kod (PIC) oluşturur. |
| Statiği iş parçacığı güvenlidir | Yerel statiklerin iş parçacığı güvenli başlatması için C++ ABı 'da belirtilen yordamları kullanmak üzere ek kod yayar. | **Hayır** -iş parçacığı güvenli lekmelerini devre dışı bırak.<br/>**Evet** -iş parçacığı güvenli lekmelerini etkinleştirin. |
| Kayan nokta Iyileştirmesi | IEEE-754 uyumluluğunu sağlayarak kayan nokta iyileştirmeleri sunar. |
| Satır içi Yöntemler gizli | Etkinleştirildiğinde, satır içi yöntemlerin satır dışı kopyaları bildirilmiştir `private extern` . |
| Simgeler Varsayılan olarak gizlidir | Tüm semboller `private extern` , makro kullanılarak dışarı aktarmak için açıkça işaretlenmediği takdirde belirtilir `__attribute` . |
| C++ özel durumlarını etkinleştir | Derleyici tarafından kullanılan özel durum işleme modelini belirtir. | **Hayır** -özel durum işlemeyi devre dışı bırak.<br/>**Evet** -özel durum işlemeyi etkinleştir. |

## <a name="language"></a>Dil

| Özellik | Açıklama | Seçenekler |
|--|--|--|
| Run-Time türü bilgilerini etkinleştir | Çalışma zamanında C++ nesne türlerini denetlemek için kod ekler (çalışma zamanı türü bilgileri).     (frtti, FNO-rtti) |
| C dil standardı | C dil standardını belirler. | **Varsayılan**<br/>**C89** -c89 dil standardı.<br/>**C99** -C99 dil standardı.<br/>**C11** -C11 dil standardı.<br/>**C99 (GNU diyalekti)** -C99 (GNU diyalekti) dil standardı.<br/>**C11 (GNU diyalekti)** -C11 (GNU diyalekti) dil standardı. |
| C++ dil standardı | C++ dil standardını belirler. | **Varsayılan**<br/>**C++ 03** -C++ 03 dil standardı.<br/>**C++ 11** -C++ 11 dil standardı.<br/>**C++ 14** -C++ 14 dil standardı.<br/>**C++ 03 (GNU diyalekti)** -c++ 03 (GNU diyalekti) dil standardı.<br/>**C++ 11 (GNU diyalekti)** -c++ 11 (GNU diyalekti) dil standardı.<br/>**C++ 14 (GNU diyalekti)** -c++ 14 (GNU diyalekti) dil standardı. |

## <a name="advanced"></a>Gelişmiş

| Özellik | Açıklama | Seçenekler |
|--|--|--|
| Farklı derle | . C ve. cpp dosyaları için derleme dili seçeneğini belirler. (-x c,-x c++) | **Varsayılan** -. c veya. cpp uzantısına göre algıla.<br/>**C** kodu olarak derle-c kodu olarak derleyin.<br/>**C++ kodu olarak derle** -c++ kodu olarak derleyin. |
| Zorunlu Içerme dosyaları | Bir veya daha fazla zorunlu ekleme dosyası (-include \[ adı]) belirtir |

::: moniker-end
