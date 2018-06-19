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
ms.openlocfilehash: 1978c566dab949093f0ddbd2aa1aa37ad0942808
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33336196"
---
# <a name="cc-properties-linux-c"></a>C/C++ özellikleri (Linux C++)

## <a name="general"></a>Genel
Özellik | Açıklama | Seçenekler
--- | ---| ---
Ek içeren dizinler | INCLUDE yolu eklemek için bir veya daha fazla dizinleri belirtir; birden fazla ise noktalı virgülle ayırın. (-I[path]).
Hata ayıklama bilgileri biçimi | Derleyici tarafından üretilen hata ayıklama bilgi türünü belirtir. | **Hiçbiri** -derleme daha hızlı şekilde hiçbir hata ayıklama bilgilerini oluşturur.<br>**Hata ayıklama en düşük miktarda bilgiyi** -en az hata ayıklama bilgileri oluşturur.<br>**Tam hata ayıklama bilgileri (DWARF2)** -oluşturmak DWARF2 hata ayıklama bilgileri.<br>
Nesne dosya adı | Varsayılan nesne dosya adı geçersiz kılmak için bir ad belirtir; Dosya veya dizin adı olabilir. (-o [name]).
Uyarı düzeyi | Nasıl katı hakkında kod hata olarak derleyici istediğinizi belirtin.  Diğer bayraklar doğrudan ek seçenekler eklenmesi gerekir. (/ w, /Weverything). | **Tüm uyarıları devre dışı bırakma** -tüm Derleyici uyarılarını devre dışı bırakır.<br>**EnableAllWarnings** -varsayılan olarak devre dışı dahil olmak üzere tüm uyarıları sağlar.<br>
Uyarıları hata ele | Tüm derleyici uyarıları hata olarak değerlendirir. Yeni bir proje için /Werror tüm derlemeleri kullanmak en iyi yöntem olabilir; Tüm uyarıları çözümleme, en az olası Bul sabit kod kusurları güvence altına alır.
C ek uyarıları | Ek uyarı iletileri kümesini tanımlar.
C++ ek uyarıları | Ek uyarı iletileri kümesini tanımlar.
Ayrıntılı modunu etkinleştir | Ayrıntılı modu etkinleştirildiğinde, bu aracı daha fazla bilgi yazdıracak yapı tanılamak için.
C derleyicisi | C kaynak dosyası ya da uzak sistem üzerindeki C Derleyici yoluna derleme sırasında çağırmak için program belirtir.
C++ Derleyicisi | C++ kaynak dosyaları ya da uzak sistem üzerindeki C++ derleyicisi yoluna derleme sırasında çağırmak için program belirtir.
Derleme zaman aşımı | Uzak derleme, milisaniye cinsinden zaman aşımı.
Nesne dosyaları kopyalama | Derlenen Nesne dosyaları uzak sistemden yerel makineye kopyalanıp kopyalanmayacağını belirtir.

## <a name="optimization"></a>En iyi duruma getirme
Özellik | Açıklama | Seçenekler
--- | ---| ---
En iyi duruma getirme | Uygulama için en iyi duruma getirme düzeyini belirtir. | **Özel** -özel en iyi duruma getirme.<br>**Devre dışı** -iyileştirme devre dışı bırakın.<br>**Boyutu en aza** -boyutu için en iyi duruma getirme.<br>**Hızı en üst düzeye** -hızı için en iyi duruma getirme.<br>**Tam iyileştirme** -pahalı iyileştirmeler.<br>
Katı yumuşatma | Sıkı diğer ad kuralları varsayalım.  Bir türdeki bir nesne hiçbir zaman farklı türde bir nesne ile aynı adresinde bulunan olduğu kabul edilir.
Döngüler unroll | Döngüler, daha büyük kod boyutu yürütülen dalları sayısını azaltarak uygulama daha hızlı yapmayı unroll.
Bağlantı zaman iyileştirme | Nesne dosyaları, uygulamanızda arasında aramak en iyi hale getirme vererek arası yordam iyileştirmeleri etkinleştirin.
Çerçeve işaretçisini atlama | Çağrı yığınında çerçeve işaretçilerinin oluşturulmasını engeller.
Hiçbir ortak bloğu | Nesne dosyasının yerine bunları ortak blokları oluşturma veri bölümünde bile unintialized genel değişkenler ayırın

## <a name="preprocessor"></a>Ön işlemci
Özellik | Açıklama | Seçenekler
--- | ---| ---
Önişlemci tanımları | Kaynak dosyanızı önişlem simgelerini tanımlar. (-D)
Önişlemci tanımları tanımlarını Kaldır | Bir veya daha fazla önişlemci undefines belirtir.  (-U [makrosu])
Tüm önişlemci tanımları tanımlarını Kaldır | Önceden tanımlanmış tüm önişlemci değerleri tanımsız.  (-undef)
Göster içerir | Derleyici çıktı ile INCLUDE dosyaların bir listesini oluşturur.  (-H)

## <a name="code-generation"></a>Kod Üretimi
Özellik | Açıklama | Seçenekler
--- | ---| ---
Konum bağımsız kodu | Paylaşılan bir kitaplık kullanmak için konum bağımsız kod (PIC) oluşturur.
İş parçacığı içinde korumalı istatistikleri olan | C++ ABI için iş parçacığı güvenli başlatması yerel istatistikleri, belirtilen yordamları kullanmak için ek kod yayma. | **Hayır** -iş parçacığı güvenli istatistikleri devre dışı bırakın.<br>**Evet** -iş parçacığı güvenli istatistikleri etkinleştirin.<br>
Kayan nokta en iyi duruma getirme | Noktası iyileştirmeler göre sakin IEEE 754 uyumluluk kayan etkinleştirir.
Gizli satır içi yöntemleri | Etkinleştirildiğinde, satır içi yöntemleri satır dışı kopyalarını 'özel extern' bildirilir.
Varsayılan olarak simge Hiddens | Tüm sembolleri 'özel extern' açıkça '__attribute' makrosu kullanılarak verilmesi için işaretlenmiş sürece bildirilir.
C++ özel durumlarını etkinleştirin | Özel durum derleyici tarafından kullanılacak işleme modelini belirtir. | **Hayır** -özel durum işleme devre dışı bırakın.<br>**Evet** -özel durum işleme etkinleştirin.<br>

## <a name="language"></a>Dil
Özellik | Açıklama | Seçenekler
--- | ---| ---
Çalışma zamanı türü bilgileri etkinleştir | Çalışma zamanında (çalışma zamanı türü bilgileri) C++ nesne türlerini denetlemek için kod ekler.     (frtti, fno rttı)
C dili standart | C dili standart belirler. | **Default**<br>**C89** -C89 dil standardı.<br>**C99** -C99 dil standardı.<br>**C11** -C11 dil standardı.<br>**C99 (GNU Dialect)** -C99 (GNU Dialect) dil standardı.<br>**C11 (GNU Dialect)** -C11 (GNU Dialect) dil standardı.<br>
C++ dili standart | C++ dili standart belirler. | **Default**<br>**C ++ 03** -C ++ 03 dil standardı.<br>**C ++ 11** -C ++ 11 dil standardı.<br>**C ++ 14** -C ++ 14 dil standardı.<br>**C ++ 03 (GNU Dialect)** - C ++ 03 (GNU Dialect) dil standardı.<br>**C ++ 11 (GNU Dialect)** - C ++ 11 (GNU Dialect) dil standardı.<br>**C ++ 14 (GNU Dialect)** - C ++ 14 (GNU Dialect) dil standardı.<br>

## <a name="advanced"></a>Gelişmiş
Özellik | Açıklama | Seçenekler
--- | ---| ---
Olarak derleme | .C ve .cpp dosyaları için derleme dil seçeneği seçin.  'Default' temel alınarak .c veya .cpp uzantı algılar. (-x c, -x c++) | **Varsayılan** -varsayılan.<br>**C kodu olarak derleme** -C kodu olarak derleyin.<br>**C++ kodu olarak derleme** -C++ kodu olarak derleyin.<br>
Zorlanan dosyaları dahil etme | Bir veya daha fazla zorunlu içerik dosyalarını (-[name] dahil)

## <a name="additional-options"></a>Ek Seçenekler 
