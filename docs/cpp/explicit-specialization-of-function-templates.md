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
ms.openlocfilehash: c9d77cef790bdd0a65651ffb7246e685175482b1
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179997"
---
# <a name="explicit-specialization-of-function-templates"></a>İşlev Şablonlarının Açık Alt Uzmanlaşması

Bir işlev şablonuyla, bu tür için işlev şablonunun açık bir özelleştirmesi (geçersiz kılma) sağlayarak belirli bir tür için özel davranış tanımlayabilirsiniz. Örneğin:

```cpp
template<> void MySwap(double a, double b);
```

Bu bildirim, **çift** değişkenler için farklı bir işlev tanımlamanıza olanak sağlar. Şablon olmayan işlevler gibi standart tür dönüştürmeleri ( **float** türündeki bir değişkeni **ikiye**yükseltmek gibi) uygulanır.

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

[İşlev Şablonları](../cpp/function-templates.md)
