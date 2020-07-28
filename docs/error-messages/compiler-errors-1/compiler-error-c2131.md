---
title: Derleyici hatası C2131
ms.date: 02/28/2019
f1_keywords:
- C2131
helpviewer_keywords:
- C2131
ms.openlocfilehash: 9e5dc328375f720ad39ce57a3da500e0bedcb468
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220424"
---
# <a name="compiler-error-c2131"></a>Derleyici hatası C2131

> ifade bir sabit değer değerlendirmedi

**`const`** Derleme zamanında bir sabiti olarak belirtilen veya **`constexpr`** değerlendirilmeyen bir ifade. Derleyicinin, kullanıldığı noktada ifadenin değerini belirleyebilmelidir.

## <a name="example"></a>Örnek

Bu örnek, hata C2131 ve sorunun nasıl düzeltileceğini gösteren bir yol gösterir.

```cpp
// c2131.cpp
// compile by using: cl /EHsc /W4 /c c2131.cpp

struct test
{
    static const int array_size; // To fix, init array_size here.
    int size_array[array_size];  // C2131
};

const int test::array_size = 42;
```

```Output
c2131.cpp
c2131.cpp(7): error C2131: expression did not evaluate to a constant
c2131.cpp(7): note: failure was caused by non-constant arguments or reference to a non-constant symbol
c2131.cpp(7): note: see usage of 'array_size'
```

## <a name="see-also"></a>Ayrıca bkz.

[const](../../cpp/const-cpp.md)<br/>
[constexpr](../../cpp/constexpr-cpp.md)<br/>
