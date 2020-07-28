---
title: İşlev Şablonlarının Açık Alt Uzmanlaşması
ms.date: 11/04/2016
helpviewer_keywords:
- overriding, functions
- function templates, specialization
- explicit specialization of function templates
- declaring functions [C++], specialization of function template
- specialization of function templates
ms.assetid: eb0fcb73-eaed-42a1-9b83-14b055a34bf8
ms.openlocfilehash: 638b5dbca1b3c0c9b9c9c946418ea70354ff6266
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220567"
---
# <a name="explicit-specialization-of-function-templates"></a>İşlev Şablonlarının Açık Alt Uzmanlaşması

Bir işlev şablonuyla, bu tür için işlev şablonunun açık bir özelleştirmesi (geçersiz kılma) sağlayarak belirli bir tür için özel davranış tanımlayabilirsiniz. Örnek:

```cpp
template<> void MySwap(double a, double b);
```

Bu bildirim, değişkenler için farklı bir işlev tanımlamanıza olanak sağlar **`double`** . Şablon olmayan işlevler gibi standart tür dönüştürmeleri (örneğin, türünde bir değişkeni yükseltme **`float`** **`double`** ) uygulanır.

## <a name="example"></a>Örnek

```cpp
// explicit_specialization.cpp
template<class T> void f(T t)
{
};

// Explicit specialization of f with 'char' with the
// template argument explicitly specified:
//
template<> void f<char>(char c)
{
}

// Explicit specialization of f with 'double' with the
// template argument deduced:
//
template<> void f(double d)
{
}
int main()
{
}
```

## <a name="see-also"></a>Ayrıca bkz.

[İşlev şablonları](../cpp/function-templates.md)
