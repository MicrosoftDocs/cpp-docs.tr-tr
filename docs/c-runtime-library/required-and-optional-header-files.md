---
title: Gerekli ve İsteğe Bağlı Başlık Dosyaları
ms.date: 11/04/2016
f1_keywords:
- c.headers
helpviewer_keywords:
- include files, required in run time
- header files, required in run time
ms.assetid: f64d0bf5-e2c3-4b42-97d0-443b3d901d9f
ms.openlocfilehash: 8d1547ae7dd3b6adb33271e93e85022f04859886
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87211612"
---
# <a name="required-and-optional-header-files"></a>Gerekli ve İsteğe Bağlı Başlık Dosyaları

Her bir çalışma zamanı yordamının açıklaması, gerekli ve isteğe bağlı ekleme veya üst bilgi (. H), bu yordamın dosyaları. Yordam veya dahili olarak adlandırılan başka bir yordam tarafından kullanılan bir tanım için işlev bildirimini almak üzere gerekli üst bilgi dosyalarının eklenmesi gerekir. İsteğe bağlı üst bilgi dosyaları genellikle önceden tanımlanmış sabitler, tür tanımları veya satır içi makroların avantajlarından yararlanmak için eklenmiştir. Aşağıdaki tabloda, isteğe bağlı üstbilgi dosyası içeriklerinin bazı örnekleri listelenmektedir:

|Tanım|Örnek|
|----------------|-------------|
|Makro tanımı|Bir kitaplık yordamı makro olarak uygulanırsa, makro tanımı özgün yordamın üstbilgi dosyasından farklı bir başlık dosyasında olabilir. Örneğin, makro, `_toupper` CTYPE başlık dosyasında tanımlanmıştır. H, işlev `toupper` STDLIB içinde bildirildiği sürece. Olsun.|
|Önceden tanımlanmış sabit|Birçok kitaplık yordamı, üst bilgi dosyalarında tanımlanan sabitlere başvurur. Örneğin, yordam, `_open` `_O_CREAT` FCNTL başlık dosyasında tanımlanan gibi sabitleri kullanır. Olsun.|
|Tür tanımı|Bazı kitaplık yordamları bir yapı döndürür veya bir yapıyı bağımsız değişken olarak alır. Örneğin, Stream Input/Output yordamları `FILE` , STDIO 'da tanımlanan türünde bir yapı kullanır. Olsun.|

Çalışma zamanı kitaplık üst bilgi dosyaları, ANSI/ISO C standardı önerilen stilinde işlev bildirimleri sağlar. Derleyici, ilişkili işlev bildiriminden sonra oluşan herhangi bir yordam başvurusunda tür denetimi gerçekleştirir. İşlev bildirimleri, varsayılan değer olan dışında bazı tür bir değer döndüren yordamlar için önemlidir **`int`** . Bildiriminde uygun dönüş değerlerini belirtmeyen yordamlar derleyici tarafından kabul edilir ve bu da **`int`** beklenmedik sonuçlara neden olabilir. Daha fazla bilgi için bkz. [tür denetimi](../c-runtime-library/type-checking-crt.md) .

## <a name="see-also"></a>Ayrıca bkz.

[CRT kitaplık özellikleri](../c-runtime-library/crt-library-features.md)
