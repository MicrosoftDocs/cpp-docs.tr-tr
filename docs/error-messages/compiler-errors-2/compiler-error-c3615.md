---
title: "Derleyici Hatası C3615 | Microsoft Docs"
ms.date: 10/24/2017
ms.technology: cpp-tools
ms.topic: error-reference
f1_keywords: C3615
dev_langs: C++
helpviewer_keywords: C3615
ms.assetid: 5ce96ba9-3d31-49f3-9aa8-24e5cdf6dcfc
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ea5502ee6e66cf3add4a4ff97e4922a66712ed70
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3615"></a>Derleyici Hatası C3615

> constexpr işlevi '*işlevi*' sabit bir ifade olamaz

İşlev *işlevi* olarak değerlendirilemedi `constexpr` derleme zamanında. Olmasını `constexpr`, bir işlev yalnızca diğer çağırabilir `constexpr` işlevleri.

## <a name="example"></a>Örnek

Visual Studio 2017 koşullu değerlendirilirken işlemi sol işleneni geçerli olmadığında bir hata doğru başlatır bir `constexpr` bağlamı. Aşağıdaki kod, Visual Studio 2015'te ancak Visual Studio 2017'de derler.

```cpp
// C3615.cpp
// Compile with: /c

template<int N>
struct myarray
{
    int size() const { return N; }
};

constexpr bool f(const myarray<1> &arr)
{
    return arr.size() == 10 || arr.size() == 11; // C3615 starting in Visual Studio 2017
}
```

Bu sorunu gidermek için ya da bildirme `array::size()` olarak işlev `constexpr` Kaldır `constexpr` niteleyicisi gelen `f`.