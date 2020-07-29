---
title: noinline
ms.date: 11/04/2016
f1_keywords:
- noinline_cpp
helpviewer_keywords:
- noinline __declspec keyword
- __declspec keyword [C++], noinline
ms.assetid: f259d55b-dec7-4bde-8cf9-14521e4fdc42
ms.openlocfilehash: bedf17072c06ec893b9cbd83b46403dcd3bc1560
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87186691"
---
# <a name="noinline"></a>noinline

**Microsoft'a Özgü**

**`__declspec(noinline)`** derleyiciye belirli bir üye işlevini (bir sınıftaki işlev) hiçbir şekilde satır içi olarak bildirir.

Küçük ve kodunuzun performansı açısından önemli olmayan bir işlevin satır içi olmaması çok daha fazla olabilir. Diğer bir deyişle, işlev küçükse ve genellikle bir hata koşulunu işleyen bir işlev gibi sık çağrılmamasından kaynaklanır.

Bir işlev işaretlenmişse **`noinline`** , çağıran işlevin daha küçük olacağını ve bu nedenle derleyicinin iç çizgisi için bir aday olduğunu aklınızda bulundurun.

```cpp
class X {
   __declspec(noinline) int mbrfunc() {
      return 0;
   }   // will not inline
};
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__declspec](../cpp/declspec.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)<br/>
[satır içi, __inline, \_ _forceinline](inline-functions-cpp.md)
