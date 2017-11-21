---
title: C++'deki Lambda ifadeleri constexpr | Microsoft Docs
ms.custom: 
ms.date: 07/19/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords: lambda expressions [C++], constexpr
ms.assetid: b56346cd-fbff-475f-aeaa-ed2010c6d6f7
caps.latest.revision: "0"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e33918193e92e432845052f875cba2e4baf22600
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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