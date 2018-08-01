---
title: constexpr Lambda ifadeleri c++ | Microsoft Docs
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
ms.openlocfilehash: b78fa3de7777ffc6702902cf967a405595caf12f
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408209"
---
# <a name="constexpr-lambda-expressions-in-c"></a>constexpr Lambda ifadeleri c++
**Visual Studio 2017 sürüm 15.3 ve üzeri** (bulunan [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): bir lambda ifadesi olarak bildirilebilir **constexpr** veya contant ifadede kullanılan zaman her başlatma yakalayan veya tanıtır veri üyesi, içinde bir sabit ifadesine izin verilir.  

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
 [C++ Dil Başvurusu](../cpp/cpp-language-reference.md)   
 [C++ Standart kitaplığındaki işlev nesneleri](../standard-library/function-objects-in-the-stl.md)   
 [İşlev çağrısı](../cpp/function-call-cpp.md)   
 [for_each](../standard-library/algorithm-functions.md#for_each)