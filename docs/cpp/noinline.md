---
title: noinline
ms.date: 11/04/2016
f1_keywords:
- noinline_cpp
helpviewer_keywords:
- noinline __declspec keyword
- __declspec keyword [C++], noinline
ms.assetid: f259d55b-dec7-4bde-8cf9-14521e4fdc42
ms.openlocfilehash: 3a8dce21aa707a1a52c647c9efee5ab806511ca8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50454567"
---
# <a name="noinline"></a>noinline

## <a name="microsoft-specific"></a>Microsoft'a Özgü

**__declspec(noinline)** belirli üye işlevi (işlevi bir sınıfa) hiçbir zaman satır içi derleyiciye bildirir.

Küçük ve kodunuzun performansını artırmak için kritik ise satır için bir işlev faydalı olabilir. Diğer bir deyişle, işlev, küçük ve sık sık çağrılacak olası değil ise, bir işlev gibi bir hata durumu işler.

Aklınızda bir işlev işaretlenmişse **noinline**, çağıran işlevin daha küçük ve bu nedenle, kendisi için satır içi derleyici bir aday olacaktır.

```cpp
class X {
   __declspec(noinline) int mbrfunc() {
      return 0;
   }   // will not inline
};
```

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__declspec](../cpp/declspec.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[Satır içi, __inline, \__forceinline](inline-functions-cpp.md)

