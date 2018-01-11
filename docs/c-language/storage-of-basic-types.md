---
title: "Temel türleri depolama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
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
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dff8df934a0c812ca798d5a1e87188e2468902ac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="storage-of-basic-types"></a>Temel Türleri Depolama
Aşağıdaki tabloda her temel türü ile ilişkili depolama özetler.  
  
### <a name="sizes-of-fundamental-types"></a>Temel türler boyutları  
  
|Tür|Depolama|  
|----------|-------------|  
|`char`, `unsigned char`, **char imzalı**|1 bayt|  
|**kısa**, **kısa imzalanmamış**|2 bayt|  
|`int`, `unsigned int`|4 bayt|  
|**uzun**,`unsigned long`|4 bayt|  
|**float**|4 bayt|  
|**double**|8 bayt|  
|`long double`|8 bayt|  
  
 C veri türleri genel kategorilere ayrılır. "Tam sayı türleri" dahil `char`, `int`, **kısa**, **uzun**, **imzalı**, `unsigned`, ve `enum`. "Kayan" türler **float**, **çift**, ve `long double`. "Aritmetik türleri" tüm kayan ve tam sayı türleri içerir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bildirimler ve Türler](../c-language/declarations-and-types.md)