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
ms.openlocfilehash: 8cd035686a07285f52fe24aa7ab4f360619d5e1f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229083"
---
# <a name="bool-c"></a>bool (C++)

Bu anahtar sözcük yerleşik bir türdür. Bu tür bir değişken, ve değerlerini içerebilir [`true`](../cpp/true-cpp.md) [`false`](../cpp/false-cpp.md) . Koşullu ifadeler türü vardır **`bool`** ve bu nedenle türünde değerlere sahiptir **`bool`** . Örneğin, `i != 0` artık **`true`** **`false`** değerine bağlıdır `i` .

**Visual Studio 2017 sürüm 15,3 ve üzeri** ( [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)ile kullanılabilir): bir sonek veya önek artırma veya azaltma işlecinin işleneni türünde olamaz **`bool`** . Diğer bir deyişle, türünde bir değişken verildiğinde `b` **`bool`** , bu ifadelere artık izin verilmez:

```cpp
    b++;
    ++b;
    b--;
    --b;
```

Değerler **`true`** ve **`false`** aşağıdaki ilişkiye sahiptir:

```cpp
!false == true
!true == false
```

Aşağıdaki deyimde:

```cpp
if (condexpr1) statement1;
```

İse `condexpr1` **`true`** , `statement1` her zaman yürütülür; ise `condexpr1` **`false`** , `statement1` hiçbir zaman yürütülmez.

Bir sonek veya önek **`++`** işleci türündeki bir değişkene uygulandığında **`bool`** , değişkeni olarak ayarlanır **`true`** .

**Visual Studio 2017 sürüm 15,3 ve üzeri**: `operator++` için **`bool`** , dilden kaldırılmış ve artık desteklenmiyor.

Sonek veya önek **`--`** işleci bu türden bir değişkene uygulanamaz.

**`bool`** Tür, varsayılan integral promosyonlara katılır. Türünde bir r-değeri **`bool`** **`int`** , **`false`** sıfır ve bir tane olmak üzere, türünün bir r-değerine dönüştürülebilir **`true`** . Farklı bir tür olarak **`bool`** aşırı yükleme çözümüne katılıyorsa.

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar sözcükler](../cpp/keywords-cpp.md)<br/>
[Yerleşik türler](../cpp/fundamental-types-cpp.md)
