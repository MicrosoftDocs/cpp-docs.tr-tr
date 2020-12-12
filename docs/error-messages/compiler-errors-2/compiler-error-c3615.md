---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3615'
title: Derleyici hatası C3615
ms.date: 10/24/2017
f1_keywords:
- C3615
helpviewer_keywords:
- C3615
ms.assetid: 5ce96ba9-3d31-49f3-9aa8-24e5cdf6dcfc
ms.openlocfilehash: 9f3b95b96ff10a99f3ebeac1bc3b19f759dd0ab7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262288"
---
# <a name="compiler-error-c3615"></a>Derleyici hatası C3615

> constexpr işlevi '*Function*' sabit ifade ile sonuçlanamaz

İşlev *işlevi* , **`constexpr`** derleme zamanında değerlendirilemiyor. Olması için **`constexpr`** , bir işlev yalnızca diğer işlevleri çağırabilir **`constexpr`** .

## <a name="example"></a>Örnek

Koşullu değerlendirme işleminin sol işleneni bağlamda geçerli olmadığında Visual Studio 2017 doğru bir şekilde hata oluşturur **`constexpr`** . Aşağıdaki kod Visual Studio 2015 ' de derlenir, ancak Visual Studio 2017 ' de değildir.

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

Bu sorunu onarmak için, `array::size()` işlevi olarak bildirir **`constexpr`** veya **`constexpr`** kümeden kaldırın `f` .
