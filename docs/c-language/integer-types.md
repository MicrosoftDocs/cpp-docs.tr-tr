---
title: Tam Sayı Türleri
ms.date: 11/04/2016
helpviewer_keywords:
- integer data type, integer types in C++
- integer constants
- integer types
- integers, types
ms.assetid: c8926a5e-0e98-4e37-9b05-ce97961379bd
ms.openlocfilehash: 0359ef3037a44ed50326d19d1c184c463adcaa5a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50563585"
---
# <a name="integer-types"></a>Tam Sayı Türleri

Her bir tamsayı sabit değeri ve ifade edilir biçimini temel alan bir tür verilir. Herhangi bir tamsayı sabiti türü zorlayabilirsiniz **uzun** harf ekleyerek **l** veya **L** türü olmasını zorlar; sabiti sonuna `unsigned` ekleyerek **u** veya **U** değer. Küçük harf **l** basamağı 1'ile karıştırılır olabilir ve kaçınılmalıdır. Bazı formları **uzun** tamsayı sabitleri izleyin:

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

Bir sabite atama türü sabiti temsil eden değerine bağlıdır. Bir sabitin değeri kendi türünün temsil edilebilir değerler aralığında olmalıdır. Hangi dönüştürme sabit bir ifadede kullanıldığında ya da zaman gerçekleştirilen bir sabitin türü belirler eksi işareti (**-**) uygulanır. Bu liste, tamsayı sabitleri için dönüştürme kuralları özetlenmektedir.

- Ondalık sabit bir soneki olmadan türü geçerli `int`, **long int**, veya **imzasız long int**. Bu üç tür sabitin değeri gösterilebilir ilk sabiti için atanan türüdür.

- Sekizlik ve onaltılık sabitler sonekleri olmadan atanan türü `int`, `unsigned int`, **long int**, veya **imzasız long int** sabiti boyutuna bağlı olarak.

- Sabitler ile atanan türü bir **u** veya **U** sonek **işaretsiz int** veya **imzasız long int** boyutlarına bağlı olarak.

- Sabitler ile atanan türü bir **l** veya **L** sonek **long int** veya **imzasız long int** boyutlarına bağlı olarak.

- Sabitler ile atanan türü bir **u** veya **U** ve **l** veya **L** sonek **imzasız long int**.

## <a name="see-also"></a>Ayrıca Bkz.

[C Tamsayı Sabitleri](../c-language/c-integer-constants.md)