---
title: Derleyici Uyarısı (düzey 3) C4839
ms.date: 09/13/2018
f1_keywords:
- C4839
helpviewer_keywords:
- C4839
ms.assetid: f4f99066-9258-4330-81a8-f4a75a1d95ee
ms.openlocfilehash: 2c238dc16359583bf55f7590d2ce7c0363d66df7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198581"
---
# <a name="compiler-warning-level-3-c4839"></a>Derleyici Uyarısı (düzey 3) C4839

> '*Type*' sınıfının, değişen sayıda bağımsız değişken işleve bağımsız değişken olarak standart olmayan kullanımı

`printf` gibi farklı bir bağımsız işleve geçirilen sınıflar veya yapılar, Üçlü kopyalanabilir olmalıdır. Bu tür nesneler geçirilirken, derleyici yalnızca bit düzeyinde bir kopya yapar ve oluşturucuyu veya yıkıcıyı çağırmaz.

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

`CStringW`kullanılarak oluşturulan ve yönetilen dizeler için, `CStringW` nesnesini biçim dizesi tarafından beklenen C işaretçisine dönüştürmek için, belirtilen `operator LPCWSTR()` kullanılmalıdır.

```cpp
    CStringW str1;
    CStringW str2;
    // ...
    str1.Format("%s", static_cast<LPCWSTR>(str2));
```
