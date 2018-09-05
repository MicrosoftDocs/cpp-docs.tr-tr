---
title: ARM Assembler yönergeleri | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
dev_langs:
- C++
ms.assetid: 9cfa8896-ec10-4e77-855a-3135c40d7d2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 282d8bbd55bec8053961c709eb3733a65972b187
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43693119"
---
# <a name="arm-assembler-directives"></a>ARM Assembler Yönergeleri

Çoğunlukla, belgelenen ARM derleme dili Microsoft ARM derleyicisi kullanan [ARM derleyici armasm Başvuru Kılavuzu](http://infocenter.arm.com/help/topic/com.arm.doc.dui0802b/index.html). Ancak, bazı derleme yönergeleri Microsoft uygulamaları ARM derleme yönergeleri farklı. Bu makalede farklar açıklanmaktadır.

## <a name="microsoft-implementations-of-arm-assembly-directives"></a>ARM derleme yönergeleri Microsoft uygulamaları

`AREA`<br/>
Microsoft ARM derleyicisi bunları destekleyen `AREA` öznitelikleri: `ALIGN`, `CODE`, `CODEALIGN`, `DATA`, `NOINIT`, `READONLY`, `READWRITE`, `THUMB`, `ARM`.

Hariç `THUMB` ve `ARM` açıklandığı gibi çalışma [ARM derleyici armasm Başvuru Kılavuzu](http://infocenter.arm.com/help/topic/com.arm.doc.dui0802b/index.html).

Microsoft ARM derleyicisi, `THUMB` belirten bir `CODE` bölümü Thumb kodu içerir ve varsayılan `CODE` bölümler.  `ARM` bölümü, ARM kodu içerdiğini gösterir.

`ATTR`<br/>
Desteklenmez.

`CODE16`<br/>
Microsoft ARM derleyicisi Project'in izin vermediği pre-UAL Thumb sözdizimi gösterdiğinden desteklenmiyor.  Kullanım `THUMB` bunun yerine, UAL söz dizimi ile birlikte yönergesi.

`COMMON`<br/>
Genel bölge için bir hizalama belirtimine desteklenmiyor.

`DCDO`<br/>
Desteklenmez.

`DN`, `QN`, `SN`<br/>
Bir türü veya bir kayıt diğer yolundaki belirtimi desteklenmiyor.

`ENTRY`<br/>
Desteklenmez.

`EQU`<br/>
Bir tür için tanımlanmış sembol belirtimi desteklenmiyor.

`EXPORT` ve `GLOBAL`

> **Dışarı aktarma** <em>sym</em>{**[**<em>türü</em>**]**}

*sym* verilecek semboldür.  [*türü*], belirtilmişse olabilir `[DATA]` sembol veri noktaları belirtmek için veya `[FUNC]` sembol kod noktaları belirtmek için.

`GLOBAL` eşanlamlıdır `EXPORT`.

`EXPORTAS`<br/>
Desteklenmez.

`FRAME`<br/>
Desteklenmez.

`FUNCTION` ve `PROC`<br/>
Özel belirtimi için derleme sözdizimi destekler; ancak Kaydet çağıran ve çağrılan tasarrufu olan kayıtları listeleyerek yordamlarını çağırma Microsoft ARM derleyicisi söz dizimini kabul eder ancak kayıt listeleri yoksayar.  Derleyici tarafından oluşturulan hata ayıklama bilgileri yalnızca için varsayılan çağırma kuralını destekler.

`IMPORT` ve `EXTERN`

> **İçeri aktarma** *sym*{**, ZAYIF** *diğer*{**, türü** *t*}}

*sym* içeri aktarılacak sembolü adıdır.

Varsa `WEAK` *diğer* belirtilirse, bu gösterir *sym* zayıf bir dış. Bunun için hiçbir tanım bağlantı zamanında bulunan sonra bağlamak yerine tüm başvuruları *diğer*.

Varsa `TYPE` *t* , ardından belirtilen *t* nasıl bağlayıcı çözümlemeye belirten *sym*.  Bu değerler için *t* mümkündür:<br/>
1 — bir kitaplık arama gerçekleştirmeyin *sym*<br/>
2 — kitaplığı araması gerçekleştirmek *sym*<br/>
3 —*sym* için bir diğer addır *diğer* (varsayılan)

`EXTERN` eşanlamlıdır `IMPORT`dışında *sym* yalnızca, geçerli derlemede ona başvurusu varsa alınır.

`MACRO`<br/>
Makro koşul kodunu tutacak bir değişken kullanımı desteklenmiyor. Varsayılan değerleri makrosu parametreler desteklenmez.

`NOFP`<br/>
Desteklenmez.

`OPT`, `TTL`, `SUBT`<br/>
Microsoft ARM derleyicisi listelerini üretmediği desteklenmiyor.

`PRESERVE8`<br/>
Desteklenmez.

`RELOC`<br/>
`RELOC n` yalnızca bir yönerge ya da veri tanımı yönergesi takip edebilirsiniz. "Yerleştirildiğinde anonim hiçbir simge" dir.

`REQUIRE`<br/>
Desteklenmez.

`REQUIRE8`<br/>
Desteklenmez.

`THUMBX`<br/>
Microsoft ARM derleyicisi Thumb 2EE yönerge kümesi desteklemediği için desteklenmez.

## <a name="see-also"></a>Ayrıca bkz.

[ARM Assembler Komut Satırı Başvurusu](../../assembler/arm/arm-assembler-command-line-reference.md)<br/>
[ARM Assembler Tanılama İletileri](../../assembler/arm/arm-assembler-diagnostic-messages.md)<br/>
