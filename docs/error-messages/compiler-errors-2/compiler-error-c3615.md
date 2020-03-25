---
title: Derleyici hatası C3615
ms.date: 10/24/2017
f1_keywords:
- C3615
helpviewer_keywords:
- C3615
ms.assetid: 5ce96ba9-3d31-49f3-9aa8-24e5cdf6dcfc
ms.openlocfilehash: c1a5b6edbc87e14de267cf962dc2b1a71dd6be12
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80200544"
---
# <a name="compiler-error-c3615"></a>Derleyici hatası C3615

> constexpr işlevi '*Function*' sabit ifade ile sonuçlanamaz

İşlev *işlevi* , derleme zamanında `constexpr` olarak değerlendirilemiyor. `constexpr`olmak için, bir işlev yalnızca diğer `constexpr` işlevlerini çağırabilir.

## <a name="example"></a>Örnek

`constexpr` bağlamında, koşullu değerlendirme işleminin sol işleneni geçerli olmadığında Visual Studio 2017 doğru bir şekilde hata oluşturur. Aşağıdaki kod Visual Studio 2015 ' de derlenir, ancak Visual Studio 2017 ' de değildir.

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

Bu sorunu onarmak için `array::size()` işlevini `constexpr` olarak bildirin ya da `f``constexpr` niteleyicisini kaldırın.
