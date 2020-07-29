---
title: Temel türleri depolama
ms.date: 10/02/2019
helpviewer_keywords:
- specifiers [C++], type
- integral types, storage
- storage [C++], types
- floating-point numbers, storage
- type specifiers [C++], sizes
- arithmetic operations [C++], types
- int data type
- short data type
- signed types [C++], storage
- long double keyword [C], storage
- long keyword [C]
- double data type, storage
- types [C], arithmetic
- integral types
- data types [C], specifiers
- storing types [C++]
- unsigned types [C++], storage
- data types [C], storage
ms.assetid: bd1f33c1-c6b9-4558-8a72-afb21aef3318
ms.openlocfilehash: 973866a912b694510d587df765ac8dd54176638e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87211677"
---
# <a name="storage-of-basic-types"></a>Temel türlerin depolanması

Aşağıdaki tabloda, her temel türle ilişkili depolama özetlenmektedir.

## <a name="sizes-of-fundamental-types"></a>Temel türlerin boyutları

|Tür|Depolama|
|----------|-------------|
|**`char`**, **`unsigned char`**, **`signed char`**|1 bayt|
|**`short`**, **`unsigned short`**|2 bayt|
|**`int`**, **`unsigned int`**|4 bayt|
|**`long`**, **`unsigned long`**|4 bayt|
|**`long long`**, **`unsigned long long`**|8 bayt|
|**`float`**|4 bayt|
|**`double`**|8 bayt|
|**`long double`**|8 bayt|

C veri türleri genel kategorilere ayrılır. *İntegral türleri* ,, **`int`** , **`char`** ve **`short`** içerir **`long`** **`long long`** . Bu türler veya ile nitelenebilir **`signed`** **`unsigned`** ve **`unsigned`** kendisi için toplu olarak kullanılabilir **`unsigned int`** . Sabit listesi türleri ( **`enum`** ), çoğu amaçla integral türleri olarak da değerlendirilir. *Kayan türler* ,, **`float`** ve içerir **`double`** **`long double`** . *Aritmetik türler* tüm kayan ve tam sayı türlerini içerir.

## <a name="see-also"></a>Ayrıca bkz.

[Bildirimler ve türler](../c-language/declarations-and-types.md)
