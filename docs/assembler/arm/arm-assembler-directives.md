---
description: 'Daha fazla bilgi edinin: ARM Assembler yönergeleri'
title: ARM Assembler Yönergeleri
ms.date: 08/30/2018
ms.assetid: 9cfa8896-ec10-4e77-855a-3135c40d7d2a
ms.openlocfilehash: 8362453f2113922c5e834d1d68583b4199cf8d4c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118124"
---
# <a name="arm-assembler-directives"></a>ARM Assembler Yönergeleri

Çoğu durumda, Microsoft ARM Assembler, [ARM derleyicisi arması başvuru kılavuzu](http://infocenter.arm.com/help/topic/com.arm.doc.dui0802b/index.html)' nda belgelenen ARM derleme dilini kullanır. Ancak, bazı derleme yönergelerinin Microsoft uygulamaları ARM derleme yönergelerinden farklıdır. Bu makalede farklar açıklanmaktadır.

## <a name="microsoft-implementations-of-arm-assembly-directives"></a>ARM derleme yönergelerinin Microsoft uygulamaları

- ALANDıR

   Microsoft ARM Assembler şu öznitelikleri destekler `AREA` : `ALIGN` , `CODE` ,, `CODEALIGN` `DATA` , `NOINIT` , `READONLY` , `READWRITE` , `THUMB` , `ARM` .

   `THUMB` `ARM` [ARM derleyicisi Armasz başvuru kılavuzu](http://infocenter.arm.com/help/topic/com.arm.doc.dui0802b/index.html)'nda belgelendiği gibi tümü hariç çalışır.

   Microsoft ARM derleyicide `THUMB` bir `CODE` bölümün Thumb kodunu içerdiğini, bölümler için de varsayılan olduğunu gösterir `CODE` .  `ARM` bölümün ARM kodu içerdiğini belirtir.

- ÖZNITELIĞI

   Desteklenmez.

- CODE16

   Microsoft ARM derleyic'nın izin vermediği, önceden sürekli parmak izi gösterdiği için desteklenmez.  `THUMB`Bunun yerine, sürekli sözdizimi ile birlikte yönergesini kullanın.

- BIRÇOK

   Ortak bölge için bir hizalama belirtimi desteklenmez.

- DCDO

   Desteklenmez.

- `DN`, `QN`, `SN`

   Yazmaç diğer adında bir tür veya kulvar belirtimi desteklenmiyor.

- GIRIŞTE

   Desteklenmez.

- EQU

   Tanımlı sembol için bir tür belirtimi desteklenmiyor.

- `EXPORT` ve `GLOBAL`

   Bu söz dizimini kullanarak dışarı aktarmaları belirtir:

   > **Dışarı aktar** | **Küresel** <em>Syd</em>{**[**<em>tür</em>**]**}

   *Syd* , aktarılacak simgedir.  [*Type*] belirtilmişse, `[DATA]` sembolün veriye işaret ettiğini veya `[FUNC]` sembolün kodun işaret ettiğini göstermek için olabilir. `GLOBAL` , için bir eş anlamlı `EXPORT` .

- DıŞARı EXPORTAS

   Desteklenmez.

- KARESINE

   Desteklenmez.

- `FUNCTION` ve `PROC`

   Derleme sözdizimi, arayan tarafından kaydedilmiş kayıtları ve aranan-Kaydet ' i listeleyen bir özel çağırma kuralı belirtimini desteklese de, Microsoft ARM Assembler söz dizimini kabul eder ancak kayıt listelerini yoksayar.  Assembler tarafından üretilen hata ayıklama bilgileri yalnızca varsayılan çağırma kuralını destekler.

- `IMPORT` ve `EXTERN`

   Bu söz dizimini kullanarak içeri aktarmaları belirtir:

   > **Içeri aktar** | **Extern** *SYK*{**, zayıf** *diğer ad*{**, tür** *t*}}

   *sye* , içeri aktarılacak simgenin adıdır.

   `WEAK` *Diğer ad* belirtilmişse, *SYI* 'nin zayıf bir dış olduğunu gösterir. Bağlantı zamanında bunun için bir tanım bulunmazsa, *diğer ad* olarak bunun yerine ona tüm başvurular bağlanır.

   `TYPE` *T* belirtildiyse, bağlayıcı, bağlayıcının  *Syd*'yi nasıl çözmesinin denendiğini gösterir.  *T* için bu değerler mümkündür:

   |Değer|Açıklama|
   |-|-|
   |1|*Syd* için kitaplık araması gerçekleştirme|
   |2|*Syd* için bir kitaplık araması gerçekleştirme|
   |3|*sya* *diğer ad* için bir diğer addır (varsayılan)|

   `EXTERN``IMPORT`, ' nin yalnızca geçerli derlemede buna  başvurular varsa içeri aktarılmasının dışında, için bir eş anlamlı olur.

- MACRO

   Bir makronun koşul kodunu tutmak için bir değişken kullanılması desteklenmez. Makro parametrelerinin varsayılan değerleri desteklenmiyor.

- NOFP

   Desteklenmez.

- `OPT`, `TTL`, `SUBT`

   Microsoft ARM derleyicisi, listeler üretmediğinden desteklenmez.

- PRESERVE8

   Desteklenmez.

- KONUMU

   `RELOC n` yalnızca bir yönergeyi veya bir veri tanımı yönergesini izleyebilir. Yeniden konumlandırılan "anonim sembol" yok.

- GEREKTIRIR

   Desteklenmez.

- REQUIRE8

   Desteklenmez.

- PARMAK x

   Microsoft ARM Assembler, Thumb-2EE yönerge kümesini desteklemediğinden desteklenmez.

## <a name="see-also"></a>Ayrıca bkz.

[ARM Assembler Command-Line başvurusu](../../assembler/arm/arm-assembler-command-line-reference.md)<br/>
[ARM Assembler tanılama Iletileri](../../assembler/arm/arm-assembler-diagnostic-messages.md)<br/>
