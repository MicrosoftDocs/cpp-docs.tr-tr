---
title: içinde constexpr lambda ifadeleriC++
ms.date: 04/08/2019
helpviewer_keywords:
- lambda expressions [C++], constexpr
ms.assetid: b56346cd-fbff-475f-aeaa-ed2010c6d6f7
ms.openlocfilehash: 9467d9e404204012df6461adacd5dc4cdbdfe71d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179581"
---
# <a name="constexpr-lambda-expressions-in-c"></a>içinde constexpr lambda ifadeleriC++

**Visual Studio 2017 sürüm 15,3 ve üzeri** ( [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)Ile kullanılabilir): bir lambda ifadesi, yakalanan veya tanıtan her bir veri üyesinin başlatılmasına bir sabit ifade dahilinde izin verildiğinde, **constexpr** olarak veya sabit bir ifadede kullanılıyor olabilir.

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

Lambda, sonucu bir **constexpr** işlevinin gereksinimlerini karşılıyorsa, dolaylı olarak **constexpr** olur:

```cpp
    auto answer = [](int n)
    {
        return 32 + n;
    };

    constexpr int response = answer(10);
```

Lambda örtük veya açık bir şekilde **constexpr**ise ve bunu bir işlev işaretçisine dönüştürürseniz, sonuçta elde edilen işlev da **constexpr**olur:

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
