---
title: noinline
ms.date: 11/04/2016
f1_keywords:
- noinline_cpp
helpviewer_keywords:
- noinline __declspec keyword
- __declspec keyword [C++], noinline
ms.assetid: f259d55b-dec7-4bde-8cf9-14521e4fdc42
ms.openlocfilehash: e155726ad1f2f3f6f0501d3aebf7fa14e620d6bd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62377408"
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
[inline, __inline, \__forceinline](inline-functions-cpp.md)
