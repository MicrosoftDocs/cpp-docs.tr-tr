---
title: C++'deki Lambda ifadeleri constexpr | Microsoft Docs
ms.custom: ''
ms.date: 07/19/2017
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- lambda expressions [C++], constexpr
ms.assetid: b56346cd-fbff-475f-aeaa-ed2010c6d6f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1e01f41aaf8b761020f57625e7cbf06f8fba2659
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="constexpr-lambda-expressions-in-c"></a>constexpr C++'deki Lambda ifadeleri
**Visual Studio 2017 15.3 ve sonraki sürümleri** (bulunan [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): lambda ifadesi olarak bildirilmelidir `constexpr` veya contant ifadede kullanılan zaman başlatma her veri üyesi olan yakalar veya tanıtır içinde bir sabit ifadesine izin verilir.  

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
Bir lambda örtülü olarak başvuruluyor `constexpr` sonucu gereksinimlerini karşılayıp karşılamadığını bir `constexpr` işlevi:
```cpp
    auto answer = [](int n) 
    {
        return 32 + n; 
    };

    constexpr int response = answer(10);
``` 
Bir lambda örtük veya açık olarak ise `constexpr`ve bir işlev işaretçisi dönüştürmek, sonuçta elde edilen işlevi de `constexpr`:

```cpp
    auto Increment = [](int n)
    {
        return n + 1;
    };

    constexpr int(*inc)(int) = Increment;
```
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Dil Başvurusu](../cpp/cpp-language-reference.md)   
 [C++ Standart Kitaplığı'nda işlev nesneleri](../standard-library/function-objects-in-the-stl.md)   
 [İşlev çağrısı](../cpp/function-call-cpp.md)   
 [for_each](../standard-library/algorithm-functions.md#for_each)