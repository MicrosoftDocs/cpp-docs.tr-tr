---
title: "Yazın Conversions (C) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- conversions, type
- type conversion
- converting types
- integral promotions
- type casts, when performed
ms.assetid: d130ee7c-03c3-48f4-af7b-1fdba0d3b086
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b1e4dede1dab1fcaf9ae4de5846539924d0095e4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="type-conversions-c"></a>Tür Dönüştürmeleri (C)
Tür dönüştürmeleri belirtilen işleci ve işlenen veya işleçleri türünü bağlıdır. Tür dönüştürmeleri aşağıdaki durumlarda gerçekleştirilir:  
  
-   Bir türde bir değer atandığında farklı bir tür veya bir işleç değişken türünü, işlenen veya işlenen bir işlem gerçekleştirmeden önce dönüştürür  
  
-   Bir türde bir değer farklı bir türe açıkça zaman atama  
  
-   Bir değeri bir işleve bağımsız değişken olarak geçirilen veya ne zaman bir tür bir işleve döndürülür  
  
 Bir karakter, kısa bir tamsayı ya da bir tamsayı bit alan tüm ya da imzalı olmadığını veya numaralandırma türü, bir nesnenin tamsayı kullanılabilir olduğunda bir ifadede kullanılabilir. Varsa bir `int` değeri dönüştürdükten sonra özgün türündeki tüm değerleri temsil edebilir `int`; Aksi takdirde dönüştürülmeden `unsigned int`. Bu işlem "tam sayı promosyon." olarak adlandırılır Tamsayı yükseltmeleri değerini korur. Diğer bir deyişle, yükseltme sonrasında değeri olarak yükseltmeden önce aynı olması sağlanır. Bkz: [olağan aritmetik dönüştürmeler](../c-language/usual-arithmetic-conversions.md) daha fazla bilgi için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İfadeler ve Atamalar](../c-language/expressions-and-assignments.md)