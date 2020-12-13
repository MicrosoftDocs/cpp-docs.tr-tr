---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4840'
title: Derleyici Uyarısı (düzey 4) C4840
ms.date: 09/13/2018
f1_keywords:
- C4840
helpviewer_keywords:
- C4840
ms.openlocfilehash: a365dc38aff1ab9811407924f7f6e554d91c6f1e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330474"
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

Kullanılarak oluşturulan ve yönetilen dizeler için `CStringW` , `operator LPCWSTR()` bir `CStringW` nesneyi, biçim dizesi tarafından beklenen C stili dize işaretçisine dönüştürmek için kullanılmalıdır:

```cpp
    CStringW str1;
    CStringW str2;
    // ...
    str1.Format("%s", static_cast<LPCWSTR>(str2));
```
