---
title: Gerekli ve İsteğe Bağlı Başlık Dosyaları
description: Gerekli ve isteğe bağlı üst bilgi dosyaları Microsoft C çalışma zamanı kitaplığı 'ndan ne zaman kullanılır?
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- c.headers
helpviewer_keywords:
- include files, required in run time
- header files, required in run time
ms.assetid: f64d0bf5-e2c3-4b42-97d0-443b3d901d9f
ms.openlocfilehash: e7947c1f601a8051de5c28fba682e90c0bdce7b6
ms.sourcegitcommit: 90c300b74f6556cb5d989802d2e80d79542f55e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/09/2021
ms.locfileid: "102514635"
---
# <a name="required-and-optional-header-files"></a>Gerekli ve İsteğe Bağlı Başlık Dosyaları

Her bir çalışma zamanı yordamının açıklaması, gerekli ve isteğe bağlı ekleme veya üst bilgi (. H), bu yordamın dosyaları. Yordam veya dahili olarak adlandırılan başka bir yordam tarafından kullanılan bir tanım için işlev bildirimini almak üzere gerekli üst bilgi dosyalarının eklenmesi gerekir. İsteğe bağlı üst bilgi dosyaları genellikle önceden tanımlanmış sabitler, tür tanımları veya satır içi makroların avantajlarından yararlanmak için eklenmiştir. Aşağıdaki tabloda, isteğe bağlı üstbilgi dosyası içeriklerinin bazı örnekleri listelenmektedir:

|Tanım|Örnek|
|----------------|-------------|
|Makro tanımı|Bir kitaplık yordamı makro olarak uygulanırsa, makro tanımı özgün yordamın üstbilgi dosyasından farklı bir başlık dosyasında olabilir. Örneğin, makro, `_toupper` CTYPE başlık dosyasında tanımlanmıştır. H, işlev `toupper` STDLIB. h içinde bildirildiği sürece.|
|Önceden tanımlanmış sabit|Birçok kitaplık yordamı, üst bilgi dosyalarında tanımlanan sabitlere başvurur. Örneğin, yordam, `_open` `_O_CREAT` FCNTL. H üstbilgi dosyasında tanımlanan gibi sabitleri kullanır.|
|Tür tanımı|Bazı kitaplık yordamları bir yapı döndürür veya bir yapıyı bağımsız değişken olarak alır. Örneğin, Stream Input/Output yordamları `FILE` , STDIO. H içinde tanımlanan türünde bir yapı kullanır.|

Çalışma zamanı kitaplık üst bilgi dosyaları, ANSI/ISO C standardı önerilen stilinde işlev bildirimleri sağlar. Derleyici, ilişkili işlev bildiriminden sonra oluşan herhangi bir yordam başvurusunda tür denetimi gerçekleştirir. İşlev bildirimleri, varsayılan değer olan dışında bazı tür bir değer döndüren yordamlar için önemlidir **`int`** . Bildiriminde uygun dönüş değerlerini belirtmeyen yordamlar derleyici tarafından kabul edilir ve bu da **`int`** beklenmedik sonuçlara neden olabilir. Daha fazla bilgi için bkz. [tür denetimi](../c-runtime-library/type-checking-crt.md) .

## <a name="see-also"></a>Ayrıca bkz.

[C çalışma zamanı (CRT) ve C++ standart kitaplığı (STL) `.lib` dosyaları](../c-runtime-library/crt-library-features.md)
