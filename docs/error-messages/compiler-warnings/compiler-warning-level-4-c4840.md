---
title: Derleyici Uyarısı (düzey 4) C4840
ms.date: 09/13/2018
f1_keywords:
- C4840
helpviewer_keywords:
- C4840
ms.openlocfilehash: 649083d66d0c7a0ef11c742e56cbfb70e2e9b75f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80185210"
---
# <a name="compiler-warning-level-4-c4840"></a>Derleyici Uyarısı (düzey 4) C4840

> '*Type*' sınıfının, değişen sayıda bağımsız değişken işleve bağımsız değişken olarak taşınabilir olmayan kullanımı

## <a name="remarks"></a>Açıklamalar

Değişen bir bağımsız değişken işleve geçirilen sınıflar veya yapılar, daha düşük bir kopyalanabilir olmalıdır. Bu tür nesneler geçirilirken, derleyici yalnızca bit düzeyinde bir kopya yapar ve oluşturucuyu veya yıkıcıyı çağırmaz.

Bu uyarı, Visual Studio 2017 ' den başlayarak kullanılabilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4840 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C4840.cpp
// compile by using: cl /EHsc /W4 C4840.cpp
#include <stdio.h>

int main()
{
    struct S {
        S(int i) : i(i) {}
        S(const S& other) : i(other.i) {}
        operator int() { return i; }
    private:
        int i;
    } s(0);

    printf("%i\n", s); // warning C4840 : non-portable use of class 'main::S'
                       // as an argument to a variadic function
    // To correct the error, you can perform a static cast
    // to convert the object before passing it:
    printf("%i\n", static_cast<int>(s));
}
```

`CStringW`kullanılarak oluşturulan ve yönetilen dizeler için, `CStringW` nesnesini biçim dizesi tarafından beklenen C stili dize işaretçisine dönüştürmek için, belirtilen `operator LPCWSTR()` kullanılmalıdır:

```cpp
    CStringW str1;
    CStringW str2;
    // ...
    str1.Format("%s", static_cast<LPCWSTR>(str2));
```
