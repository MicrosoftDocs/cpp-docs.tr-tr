---
title: Temel türleri depolama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 14c8483671e806adb9170429f2e17d4487de0cfd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46090496"
---
# <a name="storage-of-basic-types"></a>Temel Türleri Depolama

Aşağıdaki tabloda her bir temel türü ile ilişkili depolama özetlenmektedir.

### <a name="sizes-of-fundamental-types"></a>Temel türlerin boyutları

|Tür|Depolama|
|----------|-------------|
|`char`, `unsigned char`, **signed char**|1 bayt|
|**kısa**, **işaretsiz**|2 bayt|
|`int`, `unsigned int`|4 bayt|
|**uzun**, `unsigned long`|4 bayt|
|**float**|4 bayt|
|**double**|8 bayt|
|`long double`|8 bayt|

C veri türleri, genel kategoriye ayrılır. "Tam sayı türleri" dahil `char`, `int`, **kısa**, **uzun**, **imzalı**, `unsigned`, ve `enum`. "Kayan" türler **float**, **çift**, ve `long double`. "Aritmetik türleri" tüm kayan ve tam sayı türleri içerir.

## <a name="see-also"></a>Ayrıca Bkz.

[Bildirimler ve Türler](../c-language/declarations-and-types.md)