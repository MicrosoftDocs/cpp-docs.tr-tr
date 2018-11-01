---
title: Derleyici Uyarısı (düzey 1) C4789
ms.date: 11/04/2016
f1_keywords:
- C4789
helpviewer_keywords:
- C4789
ms.assetid: 5800c301-5afb-4af0-85c1-ceb54d775234
ms.openlocfilehash: f489915f07eefd0909cbcd806a590f93f674c258
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50677402"
---
# <a name="compiler-warning-level-1-c4789"></a>Derleyici Uyarısı (düzey 1) C4789

> Arabellek '*tanımlayıcı*' boyutunun *N* bayt taşması; *M* bayt uzaklığında başlayarak yazılacak *m*

## <a name="remarks"></a>Açıklamalar

Uyarır belirli C çalışma zamanı (CRT) işlevleri kullanıldığında, arabellek hakkında parametreleri olarak geçirilir ve atamaları gerçekleştirilir, veri boyutları derleme zamanında bilinen şekilde. Bu uyarı, tipik veri boyutu uyuşmazlığı algılaması elude durumlar için değil.

Veri uzunluğu, bilinen, derleme zamanı, kopyalanır ve boyutu veri için çok küçük olacak şekilde derleme zamanında bilinen bir veri bloğu yerleştirerek uyarı görüntülenir. Aşağıdaki CRT işlevleri birinin iç formu kullanarak kopyalama yapılması gerekir:

- [strcpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)

- [memset](../../c-runtime-library/reference/memset-wmemset.md)

- [memcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md), [wmemcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)

Uyarı, bir parametre veri türü bir tür dönüştürme kullanılarak eşleşmeyen ve bir lvalue başvurusuna bir kopya atamasından sonra denenir da görünür.

Visual C++ olmayan hiç olmadığı kadar yürütülen kod yolu için bu uyarı oluşturabilir. Kullanarak geçici olarak uyarı devre dışı bırakabilirsiniz `#pragma`, bu örnekte gösterildiği gibi:

```cpp
#pragma(push)
#pragma warning ( disable : 4789 )
// unused code that generates compiler warning C4789`
#pragma(pop)
```

Bu, Visual C++, belirli bir kod bloğunu için uyarı oluşturmasını tutar. `#pragma(push)` Önce mevcut durumu korur `#pragma warning(disable: 4789)` değiştirir. `#pragma(pop)` Gönderilen durumunu geri yükler ve etkilerini kaldırır `#pragma warning(disable:4789)`. C++ önişlemci yönergesi hakkında daha fazla bilgi için `#pragma`, bkz: [uyarı](../../preprocessor/warning.md) ve [Pragma yönergeleri ve __Pragma anahtar sözcüğü](../../preprocessor/pragma-directives-and-the-pragma-keyword.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4789 oluşturur.

```cpp
// C4789.cpp
// compile with: /Oi /W1 /c
#include <string.h>
#include <stdio.h>

int main()
{
    char a[20];
    strcpy(a, "0000000000000000000000000\n");   // C4789

    char buf2[20];
    memset(buf2, 'a', 21);   // C4789

    char c;
    wchar_t w = 0;
    memcpy(&c, &w, sizeof(wchar_t));
}
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, ayrıca C4789 oluşturur.

```cpp
// C4789b.cpp
// compile with: /W1 /O2 /c
// processor: x86
short G;

void main()
{
   int * p = (int *)&G;
   *p = 3;   // C4789 - writes an int through a pointer to short
}
```