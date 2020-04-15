---
title: C/C++ Özellikleri (Linux C++)
ms.date: 06/07/2019
ms.assetid: 4bb8894b-c874-4a68-935e-b127d54e484f
f1_keywords: []
ms.openlocfilehash: 394cb501b4df6caed6a358ffa96ce0de5d187ae1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "79441480"
---
# <a name="cc-properties-linux-c"></a>C/C++ Özellikleri (Linux C++)

::: moniker range="vs-2015"

Linux desteği Visual Studio 2017 ve sonrası sürümlerinde kullanılabilir.

::: moniker-end

::: moniker range=">=vs-2017"

## <a name="general"></a>Genel

| Özellik | Açıklama | Seçenekler |
|--|--|--|
| Ek Dahil Dizinler | İçle yoluna eklemek için bir veya daha fazla dizin belirtir. Birden çok dizinleri ayırmak için yarı iki nokta üst üste kullanın. (-I\[yolu]). |
| Hata Ayıklama Bilgi Biçimi | Derleyici tarafından oluşturulan hata ayıklama bilgilerinin türünü belirtir. | **Yok** - Hata ayıklama bilgisi üretmez, bu nedenle derleme daha hızlı olabilir.<br/>**En az hata ayıklama bilgileri** - En az hata ayıklama bilgileri oluşturun.<br/>**Tam Hata Ayıklama Bilgileri (CÜCE2)** - CÜCE2 hata ayıklama bilgilerini oluşturun.<br/> |
| Nesne Dosya Adı | Varsayılan nesne dosya adını geçersiz kılmak için bir ad belirtir. Bir dosya veya dizin adı olabilir. (-o [isim]). |
| Uyarı Düzeyi | Derleyicinin kod hataları yla ilgili ne kadar katı olmasını istediğinizi seçer.  Diğer bayrakları doğrudan **Ek Seçenekler'e**ekleyin. (/w, /Weverything). | **Tüm Uyarıları Kapat** - Tüm derleyici uyarılarını devre dışı bırak.<br/>**EnableAllWarnings** - Varsayılan olarak devre dışı bırakılanlar da dahil olmak üzere tüm uyarıları etkinleştirin.<br/> |
| Uyarıları hata olarak ele ada | Tüm derleyici uyarılarını hata olarak ele akurum. Yeni bir proje için, tüm derlemelerde /Werror kullanmak en iyi şey olabilir. Bulunması mümkün olan en az zor kod hatalarını sağlamak için tüm uyarıları çözümle. |
| C Ek Uyarılar | Ek uyarı iletileri kümesi tanımlar. |
| C++ Ek Uyarılar | Ek uyarı iletileri kümesi tanımlar. |
| Verbose modunu etkinleştirme | Verbose modu etkinleştirildiğinde, yapıyı tanılamak için daha fazla bilgi yazdırır. |
|  C Derleyicisi | C kaynak dosyalarının derlemesi sırasında çağırmak için program veya uzak sistemde C derleyicisi için yol belirtir. |
| C++ Derleyicisi | C++ kaynak dosyalarının derlemesi sırasında çağırmak için programı veya uzak sistemdeki C++ derleyicisine giden yolu belirtir. |
| Zaman Aşım'ı Derle | Uzaktan derleme zaman, milisaniye cinsinden. |
| Nesne Dosyalarını Kopyalama | Derlenen nesne dosyalarının uzak sistemden yerel makineye kopyalanıp kopyalanmayacağını belirtir. |

## <a name="optimization"></a>İyileştirme

| Özellik | Açıklama | Seçenekler |
|--|--|--|
| İyileştirme | Uygulama için en iyi duruma getirilmesi düzeyini belirtir. | **Özel** - Özel optimizasyon.<br/>**Devre Dışı -** Optimizasyonu devre dışı.<br/>**Boyutu Simge durumuna Küçült -** Boyut için optimize edin.<br/>**Hızı En Üst Düzeye Çıkarın** - Hız için optimize edin.<br/>**Tam Optimizasyon** - Pahalı optimizasyonlar. |
| Sıkı Aliasing | En katı takma adı gerektiren kuralları varsayar.  Bir türdeki bir nesnenin, farklı bir türdeki bir nesneyle aynı adrese sahip olduğu asla varsayılmaz. |
| Döngüleri Unroll | Daha büyük kod boyutu pahasına, yürütülen şube sayısını azaltarak uygulamayı daha hızlı yapmak için döngüleri undevirir. |
| Bağlantı Süresi Optimizasyonu | En iyi duruma getiricinin uygulamanızdaki nesne dosyalarına bakmasını sağlayarak yordamlar arası optimizasyonları sağlar. |
| Çerçeve İşaretçisini Atla | Çağrı yığınında çerçeve işaretçilerinin oluşturulmasını engeller. |
| Ortak Blok Yok | Nesne dosyasının veri bölümünde, ortak bloklar olarak oluşturmak yerine, başlatif hale getirilmemiş global değişkenleri bile ayırır. |

## <a name="preprocessor"></a>Ön işlemci

| Özellik | Açıklama | Seçenekler |
|--|--|--|
| Önişlemci Tanımları | Kaynak dosyanız için ön işleme sembolleri tanımlar. (-D) |
| Tanımsız Önİşlemci Tanımları | Bir veya daha fazla önişlemci tanımlanmamış belirtir.  (-U \[makro]) |
| Tüm Önİşlemci Tanımlarını Tanımlamıyor | Daha önce tanımlanmış tüm önişlemci değerlerini tanımlamıyor.  (-def olmayan) |
| Göster Içerir | Derleyici çıktısı içeren dosyaların listesini oluşturur.  (-H) |

## <a name="code-generation"></a>Kod Üretimi

| Özellik | Açıklama | Seçenekler |
|--|--|--|
| Konum Bağımsız Kodu | Paylaşılan bir kitaplıkta kullanılmak üzere konumbağımsız kod (PIC) oluşturur. |
| Statik iplik güvenlidir | Yerel statiklerin iş parçacığı güvenli başlatılması için C++ ABI'de belirtilen yordamları kullanmak için ek kod yayır. | **Hayır** - İş parçacığı güvenli statik devre dışı.<br/>**Evet** - İş parçacığı güvenli statik etkinleştirin. |
| Kayan Nokta Optimizasyonu | IEEE-754 uyumluluğunu gevşeterek kayan nokta optimizasyonları sağlar. |
| Gizli Satır Dametleri | Etkinleştirildiğinde, satır içi yöntemlerin satır dışı kopyaları bildirilir. `private extern` |
| Varsayılan Olarak Gizlenmiş Semboller | Makro kullanılarak dışa aktarılmak üzere açıkça işaretlenmediği sürece tüm semboller beyan edilir. `private extern` `__attribute` |
| C++ Özel Durumlarını Etkinleştir | Derleyici tarafından kullanılan özel durum işleme modelini belirtir. | **Hayır** - Özel durum işlemeyi devre dışı.<br/>**Evet** - Özel durum işlemeyi etkinleştirin. |

## <a name="language"></a>Dil

| Özellik | Açıklama | Seçenekler |
|--|--|--|
| Çalışma Zamanı Türü Bilgilerini Etkinleştirme | Çalışma zamanında C++ nesne türlerini denetlemek için kod ekler (çalışma zamanı türü bilgileri).     (frtti, fno-rtti) |
| C Dil Standardı | C dil standardını belirler. | **Varsayılan**<br/>**C89** - C89 Dil Standardı.<br/>**C99** - C99 Dil Standardı.<br/>**C11** - C11 Dil Standardı.<br/>**C99 (GNU Lehçesi)** - C99 (GNU Lehçesi) Dil Standardı.<br/>**C11 (GNU Lehçesi)** - C11 (GNU Lehçesi) Dil Standardı. |
| C++ Dil Standardı | C++ dil standardını belirler. | **Varsayılan**<br/>**C++03** - C++03 Dil Standardı.<br/>**C++11** - C++11 Dil Standardı.<br/>**C++14** - C++14 Dil Standardı.<br/>**C++03 (GNU Lehçesi)** - C++03 (GNU Lehçesi) Dil Standardı.<br/>**C++11 (GNU Lehçesi)** - C++11 (GNU Lehçesi) Dil Standardı.<br/>**C++14 (GNU Lehçesi)** - C++14 (GNU Lehçesi) Dil Standardı. |

## <a name="advanced"></a>Gelişmiş

| Özellik | Açıklama | Seçenekler |
|--|--|--|
| As'ı Derle | .c ve .cpp dosyaları için derleme dili seçeneğini seçer. (-x c, -x c++) | **Varsayılan** - .c veya .cpp uzantısına göre algıla.<br/>**C Kodu olarak derleme** - C kodu olarak derleme.<br/>**C++ Kodu olarak derleme** - C++ kodu olarak derleme. |
| Zorunlu Dosya Ekleme | Bir veya daha fazla zorla dosya \[ekleme (-include adı]) belirtir |

::: moniker-end
