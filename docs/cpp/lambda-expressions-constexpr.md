---
title: C++'ta constexpr lambda ifadeleri
ms.date: 04/08/2019
helpviewer_keywords:
- lambda expressions [C++], constexpr
ms.assetid: b56346cd-fbff-475f-aeaa-ed2010c6d6f7
ms.openlocfilehash: d1bc60a6da813e54c857da38b0164f544216be00
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62368701"
---
# <a name="constexpr-lambda-expressions-in-c"></a>C++'ta constexpr lambda ifadeleri

**Visual Studio 2017 sürüm 15.3 ve üzeri** (bulunan [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): Bir lambda ifadesi olarak bildirilebilir **constexpr** veya sabit bir ifade içinde yakalayan veya tanıtır her bir veri üyesinin başlatılması izin verildiğinde sabit bir ifadede kullanılamaz.

```cpp
    int y = 32;
    auto answer = [y]() constexpr
    {
        int x = 10;
        return y + x;
    };

    constexpr int Increment(int n)
    {
        return [n] { return n + 1; }();
    }
```

Bir lambda örtülü olarak başvuruluyor **constexpr** sonucunu gereksinimlerini karşılayıp karşılamadığını bir **constexpr** işlevi:

```cpp
    auto answer = [](int n)
    {
        return 32 + n;
    };

    constexpr int response = answer(10);
```

Bir lambda, örtük veya açık ise **constexpr**ve bir işlev işaretçisine dönüştürme, elde edilen işlevi ayrıca **constexpr**:

```cpp
    auto Increment = [](int n)
    {
        return n + 1;
    };

    constexpr int(*inc)(int) = Increment;
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)<br/>
[C++ Standart Kitaplığındaki İşlev Nesneleri](../standard-library/function-objects-in-the-stl.md)<br/>
[İşlev Çağrısı](../cpp/function-call-cpp.md)<br/>
[for_each](../standard-library/algorithm-functions.md#for_each)