---
title: bool (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- bool_cpp
- __BOOL_DEFINED
dev_langs: C++
helpviewer_keywords:
- bool keyword [C++]
- __BOOL_DEFINED macro
ms.assetid: 9abed3f2-d21c-4eb4-97c5-716342e613d8
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 564d2f4849d1725d46d92562e2ce75b2ea2e2d44
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="bool-c"></a>bool (C++)
Bu anahtar sözcük yerleşik bir türdür. Bu tür bir değişken değerlere sahip olabilir [true](../cpp/true-cpp.md) ve [false](../cpp/false-cpp.md). Koşullu deyimler türüne sahip `bool` , bu nedenle türü değerleri `bool`. Örneğin, `i!=0` artık **true** veya **false** değerine bağlı olarak `i`.  

**Visual Studio 2017 15.3 ve sonraki sürümleri** (bulunan [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): işleneni bir sonek veya önek artırma veya azaltma işleci türü olmayabilir `bool`. 
  
 Değerleri **true** ve **false** aşağıdaki ilişkisine sahip:  
  
```  
!false == true  
!true == false  
```  
  
 Aşağıdaki deyimde:  
  
```  
if (condexpr1) statement1;   
```  
  
 Varsa `condexpr1` olan **true**, `statement1` her zaman; varsa yürütülür `condexpr1` olan **false**, `statement1` hiçbir zaman yürütülür.  
  
 Bir sonek veya önek `++` işleci türünde bir değişken için uygulanan `bool`, değişken **doğru**. 
**Visual Studio 2017 15.3 ve sonraki sürümleri**: operator ++ bool için dilinden kaldırıldı ve artık desteklenmiyor.

Sonek veya önek `--` işleci bu tür bir değişkene uygulanamaz.  
  
 `bool` Türü tamsayı yükseltmeleri katılır. Türünde bir r `bool` türünde bir r için dönüştürülebilir `int`, ile **false** sıfır olma ve **true** olma biri. Farklı bir tür olarak `bool` aşırı yük çözüm katılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Anahtar sözcükler](../cpp/keywords-cpp.md)   
 [Temel türler](../cpp/fundamental-types-cpp.md)