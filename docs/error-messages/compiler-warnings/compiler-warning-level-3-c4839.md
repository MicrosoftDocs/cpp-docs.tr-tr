---
title: "Derleyici Uyarısı (Düzey 3) C4839 | Microsoft Docs"
ms.date: 10/25/2017
ms.technology: cpp-tools
ms.topic: error-reference
f1_keywords: C4839
dev_langs: C++
helpviewer_keywords: C4839
ms.assetid: f4f99066-9258-4330-81a8-f4a75a1d95ee
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: aee1e564ffd72b9b08d883c94311c2bca72b5aef
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4839"></a>Derleyici Uyarısı (düzey 4) C4839

> sınıfı standart kullanımını*türü*' variadic işlevi bağımsız değişken olarak

Visual Studio 2017 içinde sınıflar ya da bir variadic geçirilen yapının işlev gibi `printf` trivially copyable olması gerekir. Bu tür nesneleri geçirirken, derleyici, sadece Bitsel bir kopya oluşturur ve oluşturucunun ya da yıkıcı çağırmaz.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4839 oluşturur:

```cpp
#include <atomic>
#include <memory>
#include <stdio.h>

int main()
{
    std::atomic<int> i(0);
    printf("%i\n", i); // error C4839: non-standard use of class 'std::atomic<int>'
                        // as an argument to a variadic function
                        // note: the constructor and destructor will not be called; 
                        // a bitwise copy of the class will be passed as the argument
                        // error C2280: 'std::atomic<int>::atomic(const std::atomic<int> &)':
                        // attempting to reference a deleted function

    struct S {
        S(int i) : i(i) {}
        S(const S& other) : i(other.i) {}
        operator int() { return i; }
    private:
        int i;
    } s(0);
    printf("%i\n", s); // warning C4840 : non-portable use of class 'main::S'
                      // as an argument to a variadic function
}
```

Hatayı düzeltmek için trivially copyable türü döndüren bir üye işlev çağrısı,

```cpp
    std::atomic<int> i(0);
    printf("%i\n", i.load());
```

Aksi takdirde geçirmeden önce nesneyi dönüştürmek için bir statik atama gerçekleştirin:

```cpp
    struct S {/* as before */} s(0);
    printf("%i\n", static_cast<int>(s))
```

Oluşturulan ve yönetilen kullanarak dizeleri için `CStringW`, sağlanan `operator LPCWSTR()` dönüştürmek için kullanılması gereken bir `CStringW` biçim dizesi tarafından beklenen C işaretçi nesnesine.

```cpp
    CStringW str1;
    CStringW str2;
    // ...
    str1.Format("%s", static_cast<LPCWSTR>(str2));
```