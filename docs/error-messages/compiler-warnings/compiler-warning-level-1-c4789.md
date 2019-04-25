---
title: Derleyici Uyarısı (düzey 1) C4789
ms.date: 03/25/2019
f1_keywords:
- C4789
helpviewer_keywords:
- C4789
ms.assetid: 5800c301-5afb-4af0-85c1-ceb54d775234
ms.openlocfilehash: 36a5032098c5caabb1b050833e487fd58679a782
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62187237"
---
# <a name="compiler-warning-level-1-c4789"></a>Derleyici Uyarısı (düzey 1) C4789

> Arabellek '*tanımlayıcı*' boyutunun *N* bayt taşması; *M* bayt uzaklığında başlayarak yazılacak *m*

## <a name="remarks"></a>Açıklamalar

**C4789** arabellek taşmalarına hakkında belirli C çalışma zamanı (CRT) işlevleri kullanıldığında uyarır. Parametre geçirilen veya atamaları yapılan boyutu uyuşmazlığı de bildirebilirsiniz. Uyarı veri boyutları, derleme zamanında biliniyorsa mümkündür. Bu uyarı, tipik veri boyutu uyuşmazlığı algılaması elude durumlar için değil.

**C4789** olduğunda uyarır verileri, derleme zamanında çok küçük olacak şekilde bilinen bir veri bloğunun içine kopyalanır.

Kopya bu CRT işlevlerden biri iç biçimini kullanıyorsa, uyarıyı oluşur:

- [strcpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)

- [memset](../../c-runtime-library/reference/memset-wmemset.md)

- [memcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md), [wmemcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)

Daha büyük bir veri türü için bir parametre türüne ve bir lvalue başvurusuna bir kopya atamasından sonra olun uyarı da görüntülenir.

Visual C++, hiçbir zaman yürüten bir kod yolu için bu uyarı oluşturabilir. Kullanarak geçici olarak uyarı devre dışı bırakabilirsiniz `#pragma`, bu örnekte gösterildiği gibi:

```cpp
#pragma warning( push )
#pragma warning( disable : 4789 )
// unused code that generates compiler warning C4789`
#pragma warning( pop )
```

Bu deyim, bu belirli kod bloğu için uyarı oluşturmasını Visual C++ tutar. `#pragma warning(push)` Önce mevcut durumu korur `#pragma warning(disable: 4789)` değiştirir. `#pragma warning(pop)` Gönderilen durumunu geri yükler ve etkilerini kaldırır `#pragma warning(disable:4789)`. Hakkında daha fazla bilgi için C++ önişlemci yönergesi `#pragma`, bkz: [uyarı](../../preprocessor/warning.md) ve [Pragma yönergeleri ve __Pragma anahtar sözcüğü](../../preprocessor/pragma-directives-and-the-pragma-keyword.md).

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