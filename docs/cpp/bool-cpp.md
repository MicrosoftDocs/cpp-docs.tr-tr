---
title: bool (C++)
ms.date: 11/04/2016
f1_keywords:
- bool_cpp
- __BOOL_DEFINED
helpviewer_keywords:
- bool keyword [C++]
- __BOOL_DEFINED macro
ms.assetid: 9abed3f2-d21c-4eb4-97c5-716342e613d8
ms.openlocfilehash: a3384bbb118c7363a603b5b9b0c8a375cb3dd185
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301645"
---
# <a name="bool-c"></a>bool (C++)

Bu anahtar sözcük yerleşik bir türdür. Bu türde bir değişken [true](../cpp/true-cpp.md) ve [false](../cpp/false-cpp.md)değerleri içerebilir. Koşullu ifadeler **bool** türüne sahiptir ve bu nedenle **bool**türünde değerlere sahiptir. Örneğin, `i!=0` artık `i`değerine bağlı olarak doğru veya yanlış olur.

**Visual Studio 2017 sürüm 15,3 ve üzeri** ( [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)ile kullanılabilir): bir sonek veya önek artırma veya azaltma işlecinin işleneni **bool**türünde olamaz. Diğer bir deyişle, **bool**türünde bir değişken `b` verildiğinde, bu ifadelere artık izin verilmez:

```cpp
    b++;
    ++b;
    b--;
    --b;
```

TRUE ve FALSE değerleri aşağıdaki ilişkiye sahiptir:

```cpp
!false == true
!true == false
```

Aşağıdaki deyimde:

```cpp
if (condexpr1) statement1;
```

`condexpr1` TRUE ise, `statement1` her zaman yürütülür; `condexpr1` FALSE ise, `statement1` hiçbir şekilde yürütülmez.

Bir sonek veya önek **++** işleci **bool**türünde BIR değişkene uygulandığında değişken true olarak ayarlanır.
**Visual Studio 2017 sürüm 15,3 ve üzeri**: **bool** için işleç + +, dilden kaldırılmıştır ve artık desteklenmiyor.

Sonek veya önek **--** işleci bu türden bir değişkene uygulanamaz.

**Bool** türü integral promosyonlara katılır. **Bool** türünde bir r-değeri, **int**türünde bir r-değerine dönüştürülebilir ve false değeri sıfır ve true olur. Farklı bir tür olarak, **bool** aşırı yükleme çözümüne katılır.

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[Yerleşik türler](../cpp/fundamental-types-cpp.md)