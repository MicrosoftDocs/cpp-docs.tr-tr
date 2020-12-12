---
title: Veri türü tanımlayıcıları ve eşdeğerleri
description: Microsoft Visual C veri türü belirticileri ve bunların eşdeğerleri açıklanmaktadır.
ms.date: 11/04/2016
helpviewer_keywords:
- type specifiers [C++], list
- widening integers
- data types [C++], equivalents
- sign-extending integral types
- zero-extending
- identifiers, data type
- data types [C++], specifiers
- simple types, names
- type names [C++], simple
ms.openlocfilehash: 6a1231bc19617dddf1cc01d4c5e7db2863f1055f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207052"
---
# <a name="data-type-specifiers-and-equivalents"></a>Veri türü tanımlayıcıları ve eşdeğerleri

Bu belge genel olarak, uzun formlar yerine aşağıdaki tabloda listelenen tür Belirticilerinin formlarını kullanır. Ayrıca, **`char`** türün varsayılan olarak imzalandığını varsayar. Bu belge boyunca **`char`** ile eşdeğerdir **`signed char`** .

## <a name="type-specifiers-and-equivalents"></a>Tür tanımlayıcıları ve eşdeğerleri

| Tür Tanımlayıcısı | Eşdeğerleri |
|--|--|
| **`signed char`**<sup>1</sup> | **`char`** |
| **`signed int`** | **`signed`**, **`int`** |
| **`signed short int`** | **`short`**, **`signed short`** |
| **`signed long int`** | **`long`**, **`signed long`** |
| **`unsigned char`** | — |
| **`unsigned int`** | **`unsigned`** |
| **`unsigned short int`** | **`unsigned short`** |
| **`unsigned long int`** | **`unsigned long`** |
| **`float`** | — |
| **`long double`**<sup>iki</sup> | — |

<sup>1</sup> **`char`** türü varsayılan olarak imzasız yaptığınızda ( **`/J`** derleyici seçeneğini belirterek), **`signed char`** olarak kısaltabilirsiniz **`char`** .

<sup>2</sup> 32 bit ve 64 bit işletim sistemlerinde, Microsoft C derleyicisi **`long double`** türü ile eşlenir **`double`** .

**Microsoft 'a özgü**

**`/J`** Varsayılan türünü olarak değiştirmek için derleyici seçeneğini belirtebilirsiniz **`char`** **`signed char`** **`unsigned char`** . Bu seçenek etkin olduğunda, **`char`** ile aynı anlamına gelir **`unsigned char`** ve **`signed`** imzalı bir karakter değeri bildirmek için anahtar sözcüğünü kullanmanız gerekir. Bir **`char`** değer açıkça bildirilirse **`signed`** , **`/J`** seçenek bunu etkilemez ve bir türe iletildiklerinde olduğunda değer, işaret genişletilir **`int`** . Tür **`char`** iletildiklerinde olduğunda tür sıfır genişletilir **`int`** .

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[C tür belirticileri](../c-language/c-type-specifiers.md)
