---
title: noinline
ms.date: 11/04/2016
f1_keywords:
- noinline_cpp
helpviewer_keywords:
- noinline __declspec keyword
- __declspec keyword [C++], noinline
ms.assetid: f259d55b-dec7-4bde-8cf9-14521e4fdc42
ms.openlocfilehash: 6e424846c46dd50852b62008c4f1f38827da849c
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857417"
---
# <a name="noinline"></a>noinline

**Microsoft 'a özgü**

**__declspec (noinline)** , derleyiciye belirli bir üye işlevini (bir sınıftaki işlev) hiçbir şekilde satır içi olarak bildirir.

Küçük ve kodunuzun performansı açısından önemli olmayan bir işlevin satır içi olmaması çok daha fazla olabilir. Diğer bir deyişle, işlev küçükse ve genellikle bir hata koşulunu işleyen bir işlev gibi sık çağrılmamasından kaynaklanır.

Bir işlev **noinline**olarak işaretlenmişse, çağıran işlevin daha küçük olacağını ve bu nedenle derleyicinin iç çizgisi için bir aday olduğunu aklınızda bulundurun.

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
[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[satır içi, __inline, \__forceinline](inline-functions-cpp.md)
