---
title: Derleyici Uyarısı (düzey 4) C4840 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2018
ms.topic: error-reference
f1_keywords:
- C4840
dev_langs:
- C++
helpviewer_keywords:
- C4840
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0baf70ac7fd4d07958478d2eef455c7dc395e221
ms.sourcegitcommit: 87d317ac62620c606464d860aaa9e375a91f4c99
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2018
ms.locfileid: "45601791"
---
# <a name="compiler-warning-level-4-c4840"></a>Derleyici Uyarısı (düzey 4) C4840

> sınıfının taşınabilir olmayan kullanımı*türü*' bir bağımsız değişken içeren işlev bağımsız değişkeni olarak
  
## <a name="remarks"></a>Açıklamalar

Sınıf ya da bir bağımsız değişken içeren işleve geçirilen yapının artık önemsiz olarak kopyalanabilir olmalıdır. Bu tür nesneleri geçirirken, derleyici, basit bit düzeyinde bir kopya oluşturur ve oluşturucu veya yıkıcı çağırmaz.

Bu uyarı, Visual Studio 2017'de kullanılabilir başlangıcıdır.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4840 oluşturur ve bu sorunun nasıl gösterir:

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

Oluşturulan ve yönetilen kullanarak dizeleri `CStringW`, sağlanan `operator LPCWSTR()` dönüştürme için kullanılması gereken bir `CStringW` biçim dizesi tarafından beklenen C stili dize işaretçisine nesnesi:

```cpp
    CStringW str1;
    CStringW str2;
    // ...
    str1.Format("%s", static_cast<LPCWSTR>(str2));
```