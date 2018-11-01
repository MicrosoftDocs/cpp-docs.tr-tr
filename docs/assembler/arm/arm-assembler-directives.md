---
title: ARM Assembler Yönergeleri
ms.date: 08/30/2018
ms.assetid: 9cfa8896-ec10-4e77-855a-3135c40d7d2a
ms.openlocfilehash: 9124f893b3334e0893073332c9d5f5a1388373d9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50592458"
---
# <a name="arm-assembler-directives"></a>ARM Assembler Yönergeleri

Çoğunlukla, belgelenen ARM derleme dili Microsoft ARM derleyicisi kullanan [ARM derleyici armasm Başvuru Kılavuzu](http://infocenter.arm.com/help/topic/com.arm.doc.dui0802b/index.html). Ancak, bazı derleme yönergeleri Microsoft uygulamaları ARM derleme yönergeleri farklı. Bu makalede farklar açıklanmaktadır.

## <a name="microsoft-implementations-of-arm-assembly-directives"></a>ARM derleme yönergeleri Microsoft uygulamaları

- ALAN

   Microsoft ARM derleyicisi bunları destekleyen `AREA` öznitelikleri: `ALIGN`, `CODE`, `CODEALIGN`, `DATA`, `NOINIT`, `READONLY`, `READWRITE`, `THUMB`, `ARM`.

   Hariç `THUMB` ve `ARM` açıklandığı gibi çalışma [ARM derleyici armasm Başvuru Kılavuzu](http://infocenter.arm.com/help/topic/com.arm.doc.dui0802b/index.html).

   Microsoft ARM derleyicisi, `THUMB` belirten bir `CODE` bölümü Thumb kodu içerir ve varsayılan `CODE` bölümler.  `ARM` bölümü, ARM kodu içerdiğini gösterir.

- ATTR

   Desteklenmez.

- KODU16

   Microsoft ARM derleyicisi Project'in izin vermediği pre-UAL Thumb sözdizimi gösterdiğinden desteklenmiyor.  Kullanım `THUMB` bunun yerine, UAL söz dizimi ile birlikte yönergesi.

- ORTAK

   Genel bölge için bir hizalama belirtimine desteklenmiyor.

- DCDO

   Desteklenmez.

- `DN`, `QN`, `SN`

   Bir türü veya bir kayıt diğer yolundaki belirtimi desteklenmiyor.

- GİRİŞ

   Desteklenmez.

- EQU

   Bir tür için tanımlanmış sembol belirtimi desteklenmiyor.

- `EXPORT` ve `GLOBAL`

   Dışarı aktarma şu sözdizimini kullanarak belirtir:

   > **Dışarı aktarma**|**genel** <em>sym</em>{**[**<em>türü</em>**]**}

   *sym* verilecek semboldür.  [*türü*], belirtilmişse olabilir `[DATA]` sembol veri noktaları belirtmek için veya `[FUNC]` sembol kod noktaları belirtmek için. `GLOBAL` eşanlamlıdır `EXPORT`.

- EXPORTAS

   Desteklenmez.

- ÇERÇEVE

   Desteklenmez.

- `FUNCTION` ve `PROC`

   Özel belirtimi için derleme sözdizimi destekler; ancak Kaydet çağıran ve çağrılan tasarrufu olan kayıtları listeleyerek yordamlarını çağırma Microsoft ARM derleyicisi söz dizimini kabul eder ancak kayıt listeleri yoksayar.  Derleyici tarafından oluşturulan hata ayıklama bilgileri yalnızca için varsayılan çağırma kuralını destekler.

- `IMPORT` ve `EXTERN`

   Bu söz dizimini kullanarak içeri aktarmalar belirtir:

   > **İçeri aktarma**|**EXTERN** *sym*{**, ZAYIF** *diğer*{**, türü** *t*}}

   *sym* içeri aktarılacak sembolü adıdır.

   Varsa `WEAK` *diğer* belirtilirse, bu gösterir *sym* zayıf bir dış. Bunun için hiçbir tanım bağlantı zamanında bulunan sonra bağlamak yerine tüm başvuruları *diğer*.

   Varsa `TYPE` *t* , ardından belirtilen *t* nasıl bağlayıcı çözümlemeye belirten *sym*.  Bu değerler için *t* mümkündür:

   |Değer|Açıklama|
   |-|-|
   |1.|Bir kitaplık arama gerçekleştirmeyin *sym*|
   |2|Bir kitaplık arama gerçekleştirmek *sym*|
   |3|*sym* için bir diğer addır *diğer* (varsayılan)|

   `EXTERN` eşanlamlıdır `IMPORT`dışında *sym* yalnızca, geçerli derlemede ona başvurusu varsa alınır.

- MACRO

   Makro koşul kodunu tutacak bir değişken kullanımı desteklenmiyor. Varsayılan değerleri makrosu parametreler desteklenmez.

- NOFP

   Desteklenmez.

- `OPT`, `TTL`, `SUBT`

   Microsoft ARM derleyicisi listelerini üretmediği desteklenmiyor.

- PRESERVE8

   Desteklenmez.

- RELOC

   `RELOC n` yalnızca bir yönerge ya da veri tanımı yönergesi takip edebilirsiniz. "Yerleştirildiğinde anonim hiçbir simge" dir.

- GEREKTİRİR

   Desteklenmez.

- REQUIRE8

   Desteklenmez.

- THUMBX

   Microsoft ARM derleyicisi Thumb 2EE yönerge kümesi desteklemediği için desteklenmez.

## <a name="see-also"></a>Ayrıca bkz.

[ARM Assembler Komut Satırı Başvurusu](../../assembler/arm/arm-assembler-command-line-reference.md)<br/>
[ARM Assembler Tanılama İletileri](../../assembler/arm/arm-assembler-diagnostic-messages.md)<br/>
