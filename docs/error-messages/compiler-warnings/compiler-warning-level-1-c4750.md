---
title: Derleyici Uyarısı (düzey 1) C4750
ms.date: 11/04/2016
f1_keywords:
- C4750
helpviewer_keywords:
- C4750
ms.assetid: b0b2c938-7d2a-4c36-8270-7daee15ffee3
ms.openlocfilehash: 2a6d83074f180a455e9c305fb4ca8ea270d0a593
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59037736"
---
# <a name="compiler-warning-level-1-c4750"></a>Derleyici Uyarısı (düzey 1) C4750

'identifier': işlev bir döngünün satır içine _alloca() değerine sahip

'İdentifier' işlevi satır içi genişletme, zorlar [_alloca](../../c-runtime-library/reference/alloca.md) işlevi içinde bir döngüye döngü yürütüldüğünde, yığın taşmasına neden olabilir.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. 'İdentifier' işlevi ile değiştirilmez olun [__forceinline](../../cpp/inline-functions-cpp.md) tanımlayıcısı.

1. 'İdentifier' işlev içermediğinden emin olun bir [_alloca](../../c-runtime-library/reference/alloca.md) bir döngü içinde bulunan işlev.

1. Belirtmeyin [/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md), [/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md), [/Ox](../../build/reference/ox-full-optimization.md), veya [/Og](../../build/reference/og-global-optimizations.md) derleme anahtar.

1. Bir yerde [_alloca](../../c-runtime-library/reference/alloca.md) işlevi bir [deneyin-except deyimi](../../cpp/try-except-statement.md) bir yığın taşması catch.

## <a name="example"></a>Örnek

Aşağıdaki kod örneği çağrıları `MyFunction` bir döngüye ve `MyFunction` çağrıları `_alloca` işlevi. `__forceinline` Değiştiricisine neden olur, satır içi genişletme `_alloca` işlevi.

```
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