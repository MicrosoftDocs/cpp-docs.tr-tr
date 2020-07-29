---
title: Veri Türü Tanımlayıcıları ve Eşdeğerleri
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
ms.assetid: 0d4b515a-4f68-4786-83cf-a5d43c7cb6f3
ms.openlocfilehash: bfbca4ae87d84286b94120eaf24de928ae75f3c9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87200328"
---
# <a name="data-type-specifiers-and-equivalents"></a>Veri Türü Tanımlayıcıları ve Eşdeğerleri

Bu kitap genellikle, uzun formlar yerine aşağıdaki tabloda listelenen tür Belirticilerinin formlarını kullanır ve **`char`** türün varsayılan olarak imzalandığını varsayar. Bu nedenle, bu kitabın tamamında **`char`** ile eşdeğerdir **`signed char`** .

## <a name="type-specifiers-and-equivalents"></a>Tür Tanımlayıcıları ve Eşdeğerleri

|Tür Tanımlayıcısı|Eşdeğerleri|
|--------------------|---------------------|
|**`signed char`** 1|**`char`**|
|**`signed int`**|**`signed`**, **`int`**|
|**`signed short int`**|**`short`**, **`signed short`**|
|**`signed long int`**|**`long`**, **`signed long`**|
|**`unsigned char`**|—|
|**`unsigned int`**|**`unsigned`**|
|**`unsigned short int`**|**`unsigned short`**|
|**`unsigned long int`**|**`unsigned long`**|
|**`float`**|—|
|**`long double`** iki|—|

1 **`char`** türü varsayılan olarak imzasız yaptığınızda ( **`/J`** derleyici seçeneğini belirterek), **`signed char`** olarak kısaltabilirsiniz **`char`** .

2 32 bit ve 64 bit işletim sistemlerinde, Microsoft C derleyicisi **`long double`** türü ile eşlenir **`double`** .

**Microsoft'a Özgü**

**`/J`** Varsayılan türünü olarak değiştirmek için derleyici seçeneğini belirtebilirsiniz **`char`** **`signed char`** **`unsigned char`** . Bu seçenek etkin olduğunda, **`char`** ile aynı anlamına gelir **`unsigned char`** ve **`signed`** imzalı bir karakter değeri bildirmek için anahtar sözcüğünü kullanmanız gerekir. Bir **`char`** değer açıkça bildirilirse **`signed`** , **`/J`** seçenek bunu etkilemez ve bir türe iletildiklerinde olduğunda değer, işaret genişletilir **`int`** . Tür **`char`** iletildiklerinde olduğunda tür sıfır genişletilir **`int`** .

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[C tür belirticileri](../c-language/c-type-specifiers.md)
