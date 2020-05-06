---
title: Tam Sayı Türleri
ms.date: 11/04/2016
helpviewer_keywords:
- integer data type, integer types in C++
- integer constants
- integer types
- integers, types
ms.assetid: c8926a5e-0e98-4e37-9b05-ce97961379bd
ms.openlocfilehash: 23da055b56e2ae77fed796d9ba8e7f227e572a9f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62232858"
---
# <a name="integer-types"></a>Tam Sayı Türleri

Her tamsayı sabitine, değerine ve ifade edildiği yönteme göre bir tür verilir. Bir tamsayı sabitine, sabitin sonuna **l** veya **l** harfini ekleyerek **Long** yazmak için zorlayabilirsiniz; değere **u** veya **u** değerini ekleyerek onu `unsigned` tür olmasını zorlayabilirsiniz. Küçük harf **l** , 1 basamağına karışmış olabilir ve kaçınılmalıdır. Bazı **uzun** tamsayı sabitleri şu şekilde izleyebilirsiniz:

```
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

Bir sabite atadığınız tür, sabit değerin temsil ettiği değere göre değişir. Bir sabitin değeri, türü için gösterilebilir tablo değerleri aralığında olmalıdır. Bir sabitin türü, sabit bir ifadede kullanıldığında ya da eksi işareti (**-**) uygulandığında hangi dönüştürmelerin gerçekleştirileceğini belirler. Bu liste, tamsayı sabitleri için dönüştürme kurallarını özetler.

- Soneki olmayan bir Decimal sabiti türü `int`, **long int**veya **unsigned long int**'tir. Sabit değerinin gösterilebileceği bu üç türün ilki, sabite atanan türdür.

- Sabit değer olmadan sekizlik ve onaltılı sabitlere atanan tür, `int` `unsigned int`, **long int**veya sabitin boyutuna bağlı olarak **işaretsiz long int** 'tir.

- Bir **u** veya **u** sonekine sahip sabitlere atanan tür, bunlara göre **işaretsiz int** veya **işaretsiz long int** 'tir.

- Bir **l** veya **l** sonekine sahip sabitlere atanan tür, büyüklüğüne bağlı olarak **long int** veya **unsigned long int** 'tir.

- Bir **u** veya **u** ve **l** ya da **l** sonekine sahip sabitlere atanan tür **işaretsiz long int**'tir.

## <a name="see-also"></a>Ayrıca bkz.

[C Tamsayı Sabitleri](../c-language/c-integer-constants.md)
