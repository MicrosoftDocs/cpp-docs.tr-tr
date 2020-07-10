---
title: Derleyici Uyarısı (düzey 1) C4750
description: Olası bir yığın taşması hakkında MSVC derleyici uyarısı C4750 açıklar.
ms.date: 07/08/2020
f1_keywords:
- C4750
helpviewer_keywords:
- C4750
ms.assetid: b0b2c938-7d2a-4c36-8270-7daee15ffee3
ms.openlocfilehash: 9a22bdda407b02b8723b7198d62289d39f62792d
ms.sourcegitcommit: 80c8a512b361bd84e38958beb1a1bf6db7434021
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/09/2020
ms.locfileid: "86180974"
---
# <a name="compiler-warning-level-1-c4750"></a>Derleyici Uyarısı (düzey 1) C4750

> '*tanımlayıcı*': _alloca () ile bir döngüde satır içine alınmış işlev

## <a name="remarks"></a>Açıklamalar

'*Tanımlayıcı*' işlevi, [`_alloca`](../../c-runtime-library/reference/alloca.md) bir döngü içinde işlevin satır içi genişletmesini zorlar, bu da döngü yürütüldüğünde yığın taşmasına neden olabilir.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. '*Tanımlayıcı*' işlevinin belirticiyle değiştirilmediğinden emin olun [`__forceinline`](../../cpp/inline-functions-cpp.md) .

1. '*Identifier*' işlevinin [`_alloca`](../../c-runtime-library/reference/alloca.md) döngüde yer alan bir işlev içermediğinden emin olun.

1. [`/O1`](../../build/reference/o1-o2-minimize-size-maximize-speed.md),, [`/O2`](../../build/reference/o1-o2-minimize-size-maximize-speed.md) [`/Ox`](../../build/reference/ox-full-optimization.md) Veya [`/Og`](../../build/reference/og-global-optimizations.md) derleme anahtarını belirtmeyin.

1. [`_alloca`](../../c-runtime-library/reference/alloca.md)İşlevi bir yığın taşmasını yakalayamayacak bir [try-except ifadesine](../../cpp/try-except-statement.md) yerleştirin.

## <a name="example"></a>Örnek

Aşağıdaki kod örneği `MyFunction` bir döngüsünde çağırır ve `MyFunction` `_alloca` işlevini çağırır. `__forceinline`Değiştirici, işlevin satır içi genişlemesine neden olur `_alloca` .

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
