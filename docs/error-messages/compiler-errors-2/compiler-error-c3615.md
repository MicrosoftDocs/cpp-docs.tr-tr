---
title: Derleyici Hatası C3615 | Microsoft Docs
ms.date: 10/24/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3615
dev_langs:
- C++
helpviewer_keywords:
- C3615
ms.assetid: 5ce96ba9-3d31-49f3-9aa8-24e5cdf6dcfc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ce1ab43f8e15535614cedf43dba42fef882bf87a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33253401"
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