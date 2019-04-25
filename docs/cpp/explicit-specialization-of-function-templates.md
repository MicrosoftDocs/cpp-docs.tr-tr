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
ms.openlocfilehash: 3d91383f895f1a8be983efe42f685419ca988823
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62184282"
---
# <a name="explicit-specialization-of-function-templates"></a>İşlev Şablonlarının Açık Alt Uzmanlaşması

Bir işlev şablonu ile bu tür için işlev şablonunun açık uzmanlığı (geçersiz kılma) sağlayarak, belirli bir tür için özel bir davranış tanımlayabilirsiniz. Örneğin:

```cpp
template<> void MySwap(double a, double b);
```

Bu bildirim için farklı bir işlev tanımlamanızı sağlayan **çift** değişkenleri. Gibi şablon olmayan işlevlere, standart tür dönüştürmeleri (türünde bir değişken yükseltme gibi **float** için **çift**) uygulanır.

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