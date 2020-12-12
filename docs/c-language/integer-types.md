---
description: 'Daha fazla bilgi edinin: tamsayı türleri'
title: Tam Sayı Türleri
ms.date: 07/22/2020
helpviewer_keywords:
- integer data type, integer types in C++
- integer constants
- integer types
- integers, types
ms.assetid: c8926a5e-0e98-4e37-9b05-ce97961379bd
ms.openlocfilehash: 0142a6c9394851bc65df0150db40eb2228dd0fe3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97181846"
---
# <a name="integer-types"></a>Tam Sayı Türleri

Her tamsayı sabitine, değerine ve ifade edilen yönteme göre bir tür verilir. Harfine veya sabitin sonuna ekleyerek herhangi bir tamsayı sabitine izin verebilirsiniz **`long`** **`l`** ; bir **`L`** **`unsigned`** değere ekleyerek ya da değere ekleyerek onu tür olmasını zorlayabilirsiniz **`u`** **`U`** . Küçük harf, **`l`** 1 basamağına karışmış olabilir ve kaçınılmalıdır. Bazı **`long`** tamsayı sabiti biçimleri şunlardır:

```C
/* Long decimal constants */
10L
79L

/* Long octal constants */
012L
0115L

/* Long hexadecimal constants */
0xaL or 0xAL
0X4fL or 0x4FL

/* Unsigned long decimal constant */
776745UL
778866LU
```

Bir sabite atadığınız tür, sabit değerin temsil ettiği değere göre değişir. Bir sabitin değeri, türü için gösterilebilir tablo değerleri aralığında olmalıdır. Bir sabitin türü, sabit bir ifadede kullanıldığında ya da eksi işareti () uygulandığında hangi dönüştürmelerin gerçekleştirileceğini belirler **`-`** . Bu liste, tamsayı sabitleri için dönüştürme kurallarını özetler.

- Soneki olmayan bir Decimal sabiti türü **`int`** ,, **`long int`** veya olur **`unsigned long int`** . Sabit değerinin gösterilebileceği bu üç türün ilki, sabite atanan türdür.

- Sonekler olmadan sekizli ve onaltılık sabitlere atanan tür,, **`int`** , **`unsigned int`** **`long int`** veya **`unsigned long int`** sabitin boyutuna bağlı olarak.

- Veya sonekine sahip sabitlere atanan tür **`u`** **`U`** ya da boyutlarına **`unsigned int`** bağlıdır **`unsigned long int`** .

- Veya sonekine sahip sabitlere atanan tür **`l`** **`L`** ya da boyutlarına **`long int`** bağlıdır **`unsigned long int`** .

- **`u`** OR ile **`U`** **`l`** veya **`L`** sonekine sahip sabitlere atanan tür **`unsigned long int`** .

## <a name="see-also"></a>Ayrıca bkz.

[C tamsayı sabitleri](../c-language/c-integer-constants.md)
