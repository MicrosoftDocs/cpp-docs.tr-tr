---
title: bool (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- bool_cpp
- __BOOL_DEFINED
dev_langs:
- C++
helpviewer_keywords:
- bool keyword [C++]
- __BOOL_DEFINED macro
ms.assetid: 9abed3f2-d21c-4eb4-97c5-716342e613d8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2af648b2b93d2d01eaf66f5b642b6514063577d6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="bool-c"></a>bool (C++)

Bu anahtar sözcük yerleşik bir türdür. Bu tür bir değişken değerlere sahip olabilir [true](../cpp/true-cpp.md) ve [false](../cpp/false-cpp.md). Koşullu deyimler türüne sahip `bool` , bu nedenle türü değerleri `bool`. Örneğin, `i!=0` artık **true** veya **false** değerine bağlı olarak `i`.  

**Visual Studio 2017 15.3 ve sonraki sürümleri** (bulunan [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): işleneni bir sonek veya önek artırma veya azaltma işleci türü olmayabilir **bool**. Diğer bir deyişle, bir değişken verilen **b** türü **bool**, bu deyimleri artık izin verilmiyor:

```cpp
    b++;
    ++b;
    b--;
    --b;
```
  
Değerleri **true** ve **false** aşağıdaki ilişkisine sahip:  
  
```cpp  
!false == true  
!true == false  
```  
  
Aşağıdaki deyimde:  
  
```cpp  
if (condexpr1) statement1;   
```  
  
Varsa `condexpr1` olan **true**, `statement1` her zaman; varsa yürütülür `condexpr1` olan **false**, `statement1` hiçbir zaman yürütülür.  
  
Bir sonek veya önek **++** işleci türünde bir değişken için uygulanan **bool**, değişken **doğru**. 
**Visual Studio 2017 15.3 ve sonraki sürümleri**: operator ++ için **bool** dilinden kaldırıldı ve artık desteklenmiyor.

Sonek veya önek **--** işleci bu tür bir değişkene uygulanamaz.  
  
 **Bool** türü tamsayı yükseltmeleri katılır. Türünde bir r **bool** türünde bir r için dönüştürülebilir **int**, ile **false** sıfır olma ve **true** olma biri. Farklı bir tür olarak **bool** aşırı yük çözüm katılır.  
  
## <a name="see-also"></a>Ayrıca bkz.

[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[Temel Türler](../cpp/fundamental-types-cpp.md)<br/>
