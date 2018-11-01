---
title: Derleyici Hatası C3615
ms.date: 10/24/2017
f1_keywords:
- C3615
helpviewer_keywords:
- C3615
ms.assetid: 5ce96ba9-3d31-49f3-9aa8-24e5cdf6dcfc
ms.openlocfilehash: e966295b5ab63350828ddb73d6791a9e30bb5c59
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50652224"
---
# <a name="compiler-error-c3615"></a>Derleyici Hatası C3615

> constexpr işlevi '*işlevi*' sabit bir ifade ile sonuçlanamaz

İşlev *işlevi* olarak değerlendirilemiyor `constexpr` derleme zamanında. Olmasını `constexpr`, bir işlev yalnızca diğer çağırabilirsiniz `constexpr` işlevleri.

## <a name="example"></a>Örnek

Visual Studio 2017 sol işlenen bir koşullu olarak değerlendirilmesini işleminin geçerli olmadığında bir hata doğru başlatan bir `constexpr` bağlamı. Visual Studio 2015'te ancak Visual Studio 2017 aşağıdaki kodu derler.

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

Bu sorunu gidermek için ya da bildirin `array::size()` işleve `constexpr` Kaldır `constexpr` gelen niteleyicisi `f`.