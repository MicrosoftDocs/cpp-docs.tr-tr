---
description: 'Daha fazla bilgi edinin: Işlev şablonlarının açık özelleştirmesi'
title: İşlev Şablonlarının Açık Alt Uzmanlaşması
ms.date: 11/04/2016
helpviewer_keywords:
- overriding, functions
- function templates, specialization
- explicit specialization of function templates
- declaring functions [C++], specialization of function template
- specialization of function templates
ms.assetid: eb0fcb73-eaed-42a1-9b83-14b055a34bf8
ms.openlocfilehash: c77ebce3383ba2051ac010c39a7dd0eb37b8111a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97181507"
---
# <a name="explicit-specialization-of-function-templates"></a>İşlev Şablonlarının Açık Alt Uzmanlaşması

Bir işlev şablonuyla, bu tür için işlev şablonunun açık bir özelleştirmesi (geçersiz kılma) sağlayarak belirli bir tür için özel davranış tanımlayabilirsiniz. Örneğin:

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
