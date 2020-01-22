---
title: Derleyici Uyarısı (düzey 1) C4789
ms.date: 03/25/2019
f1_keywords:
- C4789
helpviewer_keywords:
- C4789
ms.assetid: 5800c301-5afb-4af0-85c1-ceb54d775234
ms.openlocfilehash: 36278615631d017db1d1c2fc4eecf8c1612892de
ms.sourcegitcommit: a930a9b47bd95599265d6ba83bb87e46ae748949
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2020
ms.locfileid: "76518406"
---
# <a name="compiler-warning-level-1-c4789"></a>Derleyici Uyarısı (düzey 1) C4789

> *N* bayt boyutundaki arabellek '*tanımlayıcısı*' taşacaktır; *M bayt,* *L* uzaklığında başlayarak yazılacak

## <a name="remarks"></a>Açıklamalar

**C4789** belirli C çalışma zamanı (CRT) işlevleri kullanıldığında arabellek taşmaları hakkında uyarır. Ayrıca, parametreler geçirildiğinde veya atamalar yapıldığında boyut uyuşmazlıklarını da bildirebilir. Veri boyutları derleme zamanında biliniyorsa uyarı mümkündür. Bu uyarı, tipik veri boyutu uyumsuzluğu algılama elude olabilecek durumlar içindir.

**C4789** , veriler derleme zamanında çok küçük olarak bilinen bir veri bloğuna kopyalandığında uyarır.

Kopya, bu CRT işlevlerinden birinin iç biçimini kullanıyorsa uyarı oluşur:

- [strcpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)

- [memset](../../c-runtime-library/reference/memset-wmemset.md)

- [memckopyala](../../c-runtime-library/reference/memcpy-wmemcpy.md), [wmemcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)

Ayrıca, bir parametreyi daha büyük bir veri türüne aktardığınızda ve sonra lvalue başvurusundan bir kopya ataması yaptığınızda da uyarı görüntülenir.

Visual C++ , hiçbir şekilde çalıştırılmamış bir kod yolu için bu uyarıyı oluşturabilir. Aşağıdaki örnekte gösterildiği gibi `#pragma`kullanarak uyarıyı geçici olarak devre dışı bırakabilirsiniz:

```cpp
#pragma warning( push )
#pragma warning( disable : 4789 )
// unused code that generates compiler warning C4789`
#pragma warning( pop )
```

Bu deyim, görselin C++ belirli bir kod bloğu için uyarı oluşturulmasını önler. `#pragma warning(push)`, `#pragma warning(disable: 4789)` değiştirmeden önce mevcut durumu korur. `#pragma warning(pop)`, gönderilen durumu geri yükler ve `#pragma warning(disable:4789)`etkilerini ortadan kaldırır. C++ Önişlemci yönergesi `#pragma`hakkında daha fazla bilgi için bkz. [Warning](../../preprocessor/warning.md) and [pragma yönergeleri ve __pragma anahtar sözcüğü](../../preprocessor/pragma-directives-and-the-pragma-keyword.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C4789 oluşturur.

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

Aşağıdaki örnek ayrıca C4789 oluşturur.

```cpp
// C4789b.cpp
// compile with: /W1 /O2 /c
// processor: x86
short G;

int main()
{
   int * p = (int *)&G;
   *p = 3;   // C4789 - writes an int through a pointer to short
}
```
