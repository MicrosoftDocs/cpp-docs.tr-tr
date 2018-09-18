---
title: (C++) bool | Microsoft Docs
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
ms.openlocfilehash: ce07cfce4b7361486489c2f00c3e4b395c71e200
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46058516"
---
# <a name="bool-c"></a>bool (C++)

Bu anahtar sözcük yerleşik bir türdür. Bu türden bir değişkene değerler olabilir [true](../cpp/true-cpp.md) ve [false](../cpp/false-cpp.md). Koşullu ifadeler **bool** ve bu nedenle türünde değerlere sahiptir **bool**. Örneğin, `i!=0` TRUE veya FALSE değerini bağlı olarak sunuyor `i`.

**Visual Studio 2017 sürüm 15.3 ve üzeri** (bulunan [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): işlenen işleci bir sonek veya önek artırma veya azaltma türü olmayabilir **bool**. Diğer bir deyişle, bir değişken verilen `b` türü **bool**, bu deyimler artık izin verilmiyor:

```cpp
    b++;
    ++b;
    b--;
    --b;
```

TRUE ve FALSE değerleri şu ilişki vardır:

```cpp
!false == true
!true == false
```

Aşağıdaki deyimde:

```cpp
if (condexpr1) statement1;
```

Varsa `condexpr1` TRUE ise `statement1` her zaman; yürütülür `condexpr1` false değerine `statement1` asla yürütülmez.

Sonek veya önek **++** işleci türünde bir değişkene uygulandığında **bool**, değişkeni TRUE olarak ayarlanır.
**Visual Studio 2017 sürüm 15.3 ve üzeri**: operator ++ için **bool** dilinden kaldırıldı ve artık desteklenmiyor.

Sonek veya önek **--** işleci bu türden bir değişkene uygulanamaz.

**Bool** türü tamsayı yükseltmelerine katılır. Türündeki bir r **bool** bir tür için dönüştürülebilir **int**, FALSE olma sıfır ile haline TRUE. Farklı bir tür **bool** aşırı yükleme çözümlemesinde rol oynar.

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[Temel Türler](../cpp/fundamental-types-cpp.md)