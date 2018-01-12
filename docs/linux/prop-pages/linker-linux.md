---
title: "Bağlayıcı özellikleri (Linux C++) | Microsoft Docs"
ms.custom: 
ms.date: 9/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a0243a94-8164-425b-b2fe-b84ff363d546
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: 5396021410ec04baa8eb1218c676919a322ac978
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/03/2018
---
# <a name="linker-properties-linux-c"></a>Bağlayıcı özellikleri (Linux C++)

## <a name="general"></a>Genel

Özellik | Açıklama | Seçenekler
--- | ---| ---
Çıkış dosyası | Varsayılan ad ve konum bağlayıcı oluşturur programın seçeneğini geçersiz kılar. (-o).
İlerlemesini Göster | Bağlayıcı ilerleme iletilerini yazdırır.
Sürüm | Sürüm seçenek yürütülebilir dosya üstbilgisinde bir sürüm numarası koymak için bağlayıcı söyler.
Ayrıntılı çıktı etkinleştir | Verbose seçenek hata ayıklama için ayrıntılı ileti çıkışı için bağlayıcı söyler.
İzleme | İzleme seçeneği işlendikçe girdi dosyaları çıkarmak için bağlayıcı söyler.
İzleme simgeleri | Bir simge göründüğü dosyaların listesini yazdırma. (--izleme simgesi simgesi =)
Yazdırma eşleme | Yazdırma eşleme seçeneği belirten bir bağlantı harita çıktısını almak için bağlayıcı.
Çözümlenmemiş simge başvurularını raporu | Bu seçenek etkinleştirildiğinde çözümlenmemiş sembol başvuruları bildirir.
Bellek kullanımı için en iyi duruma getirme | Sembol tabloları gerektiği gibi yeniden okumaya bellek kullanımı için en iyi duruma getirme.
Paylaşılan kitaplık arama yolu | Paylaşılan kitaplık arama yolu doldurmak olanak tanır. (- rpath - bağlantı yolu =)
Ek Kitaplık dizinleri | Ortam Kitaplığı yol geçersiz kılmanıza olanak tanır. (-M klasörü).
Bağlayıcı | Programın sırasında bağlama veya uzak sistem üzerindeki bağlayıcı yolunu çağırma belirtir.
Bağlantı zaman aşımı | Milisaniye cinsinden zaman aşımı bağlama uzaktan.
Kopya çıktı | Derleme çıktı dosyası Uzak sistemden yerel makineye kopyalanıp kopyalanmayacağını belirtir.

## <a name="input"></a>Giriş

Özellik | Açıklama | Seçenekler
--- | ---| ---
Belirli varsayılan kitaplıkları yoksay | Bir veya daha fazla yok saymak için varsayılan kitaplık adını belirtir. (--dışlama kitaplıklar lib, lib)
Varsayılan kitaplıklar yoksay | Varsayılan kitaplıklar yoksay ve yalnızca belirtilen kitaplıkları explicitely arayın.
Tanımsız simge başvurularını zorla | Tanımlanmamış bir simge olarak çıktı dosyasında girilecek simgesi zorlar. (- u simgesi--tanımsız simgesi =)
Kitaplık bağımlılıkları | Bu seçenek bağlayıcı komut satırına eklenecek ek kitaplıklarını belirtme sağlar. Ek Kitaplığı 'lib' ve 'bir' uzantısı ile biten önekli bağlayıcı komut satırının sonuna eklenir.  (-lFILE)
Ek Bağımlılıklar | Bağlantı komut satırına eklenecek ek öğelerini belirtir.

## <a name="debugging"></a>Hata Ayıklama

Özellik | Açıklama | Seçenekler
--- | ---| ---
Hata ayıklayıcı sembol bilgileri | Sembol bilgilerini çıktı dosyası hata ayıklayıcı. | **Tüm içerir**<br>**Hata ayıklayıcı sembol bilgileri yalnızca atlayın**<br>**Tüm simge bilgilerini atlayın**<br>
Dosya adı eşleme | Map seçeneği kullanıcı belirtilen ada sahip bir harita dosyası oluşturmak için bağlayıcı söyler. (-Harita =)

## <a name="advanced"></a>Gelişmiş

Özellik | Açıklama | Seçenekler
--- | ---| ---
Yeniden konumlandırma sonra işareti değişkenleri salt okunur | Bu seçenek, sonra yeniden konumlandırma değişkenleri salt okunur işaretler.
Hemen işlev bağlama etkinleştir | Bu seçenek nesne hemen işlev bağlama için işaretler.
Yürütülebilir yığını gerektirmez | Bu seçenek çıktı yürütülebilir yığını gerektirmeyen olarak işaretler.
Tüm arşiv | Tüm arşiv kaynakları ve ek bağımlılıklar tüm koddan kullanır.
