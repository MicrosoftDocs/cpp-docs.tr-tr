---
description: "Daha fazla bilgi edinin: C++ ' da constexpr lambda ifadeleri"
title: C++ ' da constexpr lambda ifadeleri
ms.date: 04/08/2019
helpviewer_keywords:
- lambda expressions [C++], constexpr
ms.assetid: b56346cd-fbff-475f-aeaa-ed2010c6d6f7
ms.openlocfilehash: 4ff4b3acf4289a74f8b7320620601e0e2284d356
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333937"
---
# <a name="constexpr-lambda-expressions-in-c"></a>C++ ' da constexpr lambda ifadeleri

**Visual Studio 2017 sürüm 15,3 ve üzeri** ( [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)Ile kullanılabilir): bir lambda ifadesi, **`constexpr`** yakalayan veya tanıtan her bir veri üyesinin başlatılmasına bir sabit ifade dahilinde izin verildiğinde, sabit bir ifadede olarak bildirilemez veya kullanılabilir.

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

Bir lambda, **`constexpr`** sonucu bir işlevin gereksinimlerine uygunsa örtük bir şekilde yapılır **`constexpr`** :

```cpp
    auto answer = [](int n)
    {
        return 32 + n;
    };

    constexpr int response = answer(10);
```

Bir lambda örtük olarak veya açıkça bir **`constexpr`** işlev işaretçisine dönüştürürseniz, sonuçta elde edilen işlev de şu şekilde olur **`constexpr`** :

```cpp
    auto Increment = [](int n)
    {
        return n + 1;
    };

    constexpr int(*inc)(int) = Increment;
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ dil başvurusu](../cpp/cpp-language-reference.md)<br/>
[C++ standart kitaplığındaki işlev nesneleri](../standard-library/function-objects-in-the-stl.md)<br/>
[İşlev çağrısı](../cpp/function-call-cpp.md)<br/>
[for_each](../standard-library/algorithm-functions.md#for_each)
