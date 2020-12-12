---
description: 'Daha fazla bilgi edinin: Derleyici Uyarısı (düzey 3) C4839'
title: Derleyici Uyarısı (düzey 3) C4839
ms.date: 09/13/2018
f1_keywords:
- C4839
helpviewer_keywords:
- C4839
ms.assetid: f4f99066-9258-4330-81a8-f4a75a1d95ee
ms.openlocfilehash: a8ae0d3e3c74c62d05163edd981679e5390fb184
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332065"
---
# <a name="compiler-warning-level-3-c4839"></a>Derleyici Uyarısı (düzey 3) C4839

> '*Type*' sınıfının, değişen sayıda bağımsız değişken işleve bağımsız değişken olarak standart olmayan kullanımı

Gibi farklı bir bağımsız değişken işleve geçirilen sınıflar veya yapılar, `printf` Üçlü kopyalanabilir olmalıdır. Bu tür nesneler geçirilirken, derleyici yalnızca bit düzeyinde bir kopya yapar ve oluşturucuyu veya yıkıcıyı çağırmaz.

Bu uyarı, Visual Studio 2017 ' den başlayarak kullanılabilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4839 oluşturur:

```cpp
// C4839.cpp
// compile by using: cl /EHsc /W3 C4839.cpp
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
}
```

Hatayı düzeltmek için, üç aylık kopyalanabilir türü döndüren bir üye işlevini çağırabilirsiniz

```cpp
    std::atomic<int> i(0);
    printf("%i\n", i.load());
```

Kullanılarak oluşturulan ve yönetilen dizeler için `CStringW` , `operator LPCWSTR()` bir `CStringW` nesneyi biçim dizesi tarafından beklenen C işaretçisine dönüştürmek için kullanılmalıdır.

```cpp
    CStringW str1;
    CStringW str2;
    // ...
    str1.Format("%s", static_cast<LPCWSTR>(str2));
```
