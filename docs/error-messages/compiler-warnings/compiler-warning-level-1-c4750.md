---
title: Derleyici Uyarısı (düzey 1) C4750
ms.date: 11/04/2016
f1_keywords:
- C4750
helpviewer_keywords:
- C4750
ms.assetid: b0b2c938-7d2a-4c36-8270-7daee15ffee3
ms.openlocfilehash: 9ba0a37d2c213c35002b8e09d4377869a868d401
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175174"
---
# <a name="compiler-warning-level-1-c4750"></a>Derleyici Uyarısı (düzey 1) C4750

' tanımlayıcı ': _alloca () ile bir döngüde satır içine alınmış işlev

' Identifier ' işlevi döngü içinde [_alloca](../../c-runtime-library/reference/alloca.md) işlevinin satır içi genişletmesini zorlar ve döngü yürütüldüğünde yığın taşmasına neden olabilir.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. ' Tanımlayıcı ' işlevinin [__forceinline](../../cpp/inline-functions-cpp.md) belirticisiyle değiştirilmediğinden emin olun.

1. ' Identifier ' işlevinin döngüde bulunan [_alloca](../../c-runtime-library/reference/alloca.md) işlevi içermediğinden emin olun.

1. [/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md), [/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md), [/Ox](../../build/reference/ox-full-optimization.md)veya [/OG](../../build/reference/og-global-optimizations.md) derleme anahtarı belirtmeyin.

1. [_Alloca](../../c-runtime-library/reference/alloca.md) işlevini bir yığın taşmasını yakalayamayacak bir [try-except ifadesine](../../cpp/try-except-statement.md) yerleştirin.

## <a name="example"></a>Örnek

Aşağıdaki kod örneği bir döngüsünde `MyFunction` çağırır ve `MyFunction` `_alloca` işlevini çağırır. `__forceinline` değiştiricisi `_alloca` işlevinin satır içi genişlemesine neden olur.

```cpp
// c4750.cpp
// compile with: /O2 /W1 /c
#include <intrin.h>

char * volatile newstr;

__forceinline void myFunction(void) // C4750 warning
{
// The _alloca function does not require a __try/__except
// block because the example uses compiler option /c.
    newstr = (char * volatile) _alloca(1000);
}

int main(void)
{
    for (int i=0; i<50000; i++)
       myFunction();
    return 0;
}
```

## <a name="see-also"></a>Ayrıca bkz.

[_alloca](../../c-runtime-library/reference/alloca.md)
