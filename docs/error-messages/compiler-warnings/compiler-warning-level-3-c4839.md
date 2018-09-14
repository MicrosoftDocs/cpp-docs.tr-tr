---
title: Derleyici Uyarısı (Düzey 3) C4839 | Microsoft Docs
ms.date: 09/13/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4839
dev_langs:
- C++
helpviewer_keywords:
- C4839
ms.assetid: f4f99066-9258-4330-81a8-f4a75a1d95ee
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 14a79c6abb118fb173382be87ebda4316545c65a
ms.sourcegitcommit: 87d317ac62620c606464d860aaa9e375a91f4c99
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2018
ms.locfileid: "45601411"
---
# <a name="compiler-warning-level-3-c4839"></a>Derleyici Uyarısı (Düzey 3) C4839

> sınıfının standart dışı kullanımı*türü*' bir bağımsız değişken içeren işlev bağımsız değişkeni olarak

Sınıflar veya yapılar gibi değişen sayıda bağımsız değişken işleve geçirilen `printf` artık önemsiz olarak kopyalanabilir olması gerekir. Bu tür nesneleri geçirirken, derleyici, basit bit düzeyinde bir kopya oluşturur ve oluşturucu veya yıkıcı çağırmaz.

Bu uyarı, Visual Studio 2017'de kullanılabilir başlangıcıdır.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4839 oluşturur:

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

Hatayı düzeltmek için artık önemsiz olarak kopyalanabilir türü döndüren bir üye işlevi çağırabilir,

```cpp
    std::atomic<int> i(0);
    printf("%i\n", i.load());
```

Oluşturulan ve yönetilen kullanarak dizeleri `CStringW`, sağlanan `operator LPCWSTR()` dönüştürme için kullanılması gereken bir `CStringW` C işaretçisine biçim dizesi tarafından beklenen nesne.

```cpp
    CStringW str1;
    CStringW str2;
    // ...
    str1.Format("%s", static_cast<LPCWSTR>(str2));
```