---
title: Gerekli ve İsteğe Bağlı Başlık Dosyaları
ms.date: 11/04/2016
f1_keywords:
- c.headers
helpviewer_keywords:
- include files, required in run time
- header files, required in run time
ms.assetid: f64d0bf5-e2c3-4b42-97d0-443b3d901d9f
ms.openlocfilehash: 06f7ced45f8def05219d8869708f555a78f73cd3
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57744528"
---
# <a name="required-and-optional-header-files"></a>Gerekli ve İsteğe Bağlı Başlık Dosyaları

Her bir çalışma zamanı rutin açıklamasını içeren gerekli ve isteğe bağlı bir listesini içeren veya üst bilgi (. H), bu yordamı için dosyaları. Gerekli başlık dosyaları yordamı veya dahili olarak adlı başka bir yordam tarafından kullanılan bir tanımı için işlev bildirimi almak için dahil edilmesi gerekir. İsteğe bağlı üst bilgi dosyaları, önceden tanımlanmış sabitleri, tür tanımlarını veya satır içi makrolar yararlanmak için genellikle dahil edilir. Aşağıdaki tablo bazı örnekler isteğe bağlı üst bilgi dosyasının içeriğini listeler:

|Tanım|Örnek|
|----------------|-------------|
|Makro tanımı|Bir yordamı makro olarak uygulanmıştır, Makro tanımında özgün yordamı için üst bilgi dosyası dışındaki bir üstbilgi dosyasında olması olabilir. Örneğin, `_toupper` makrosu, CTYPE üstbilgi dosyasında tanımlanır. İşlev çalışırken H `toupper` STDLIB bildirilir. H|
|Önceden tanımlanmış sabiti|Birçok kitaplık yordamları üstbilgi dosyalarında tanımlanan sabitleri bakın. Örneğin, `_open` yordamı sabitler gibi kullanır `_O_CREAT`, FCNTL üstbilgi dosyasında tanımlanır. H|
|Tür tanımı|Bazı kitaplık yordamları, bir yapı döndürmesine veya bağımsız değişken olarak bir yapısı yansıtın. Örneğin, yapı türünü stream giriş/çıkış yordamlarını kullanmak `FILE`, STDIO içinde tanımlanır. H|

Çalışma Zamanı Kitaplığı üst bilgi dosyaları, ANSI/ISO C Standart önerilen stil İşlev bildirimlerinde sağlar. Derleyici, tür, ilişkilendirilmiş işlev bildiriminden sonra ortaya çıkan herhangi bir rutin başvurusu üzerinde denetimi gerçekleştirir. İşlev bildirimleri dışında bazı türünde bir değer döndüren yordam için özellikle önemli `int`, varsayılan değerdir. Uygun belirtmeyin yordamlarını döndürür, bildirimindeki değer döndürmek için derleyici tarafından değerlendirilir bir `int`, beklenmeyen sonuçlara neden. Bkz: [tür denetimi](../c-runtime-library/type-checking-crt.md) daha fazla bilgi için.

## <a name="see-also"></a>Ayrıca bkz.

[CRT Kitaplık Özellikleri](../c-runtime-library/crt-library-features.md)
