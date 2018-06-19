---
title: Yazın Conversions (C) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- conversions, type
- type conversion
- converting types
- integral promotions
- type casts, when performed
ms.assetid: d130ee7c-03c3-48f4-af7b-1fdba0d3b086
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e06da627d18fa643cb64fda870c986264c573641
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32387245"
---
# <a name="type-conversions-c"></a>Tür Dönüştürmeleri (C)
Tür dönüştürmeleri belirtilen işleci ve işlenen veya işleçleri türünü bağlıdır. Tür dönüştürmeleri aşağıdaki durumlarda gerçekleştirilir:  
  
-   Bir türde bir değer atandığında farklı bir tür veya bir işleç değişken türünü, işlenen veya işlenen bir işlem gerçekleştirmeden önce dönüştürür  
  
-   Bir türde bir değer farklı bir türe açıkça zaman atama  
  
-   Bir değeri bir işleve bağımsız değişken olarak geçirilen veya ne zaman bir tür bir işleve döndürülür  
  
 Bir karakter, kısa bir tamsayı ya da bir tamsayı bit alan tüm ya da imzalı olmadığını veya numaralandırma türü, bir nesnenin tamsayı kullanılabilir olduğunda bir ifadede kullanılabilir. Varsa bir `int` değeri dönüştürdükten sonra özgün türündeki tüm değerleri temsil edebilir `int`; Aksi takdirde dönüştürülmeden `unsigned int`. Bu işlem "tam sayı promosyon." olarak adlandırılır Tamsayı yükseltmeleri değerini korur. Diğer bir deyişle, yükseltme sonrasında değeri olarak yükseltmeden önce aynı olması sağlanır. Bkz: [olağan aritmetik dönüştürmeler](../c-language/usual-arithmetic-conversions.md) daha fazla bilgi için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İfadeler ve Atamalar](../c-language/expressions-and-assignments.md)