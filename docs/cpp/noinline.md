---
description: 'Daha fazla bilgi edinin: noinline'
title: noinline
ms.date: 11/04/2016
f1_keywords:
- noinline_cpp
helpviewer_keywords:
- noinline __declspec keyword
- __declspec keyword [C++], noinline
ms.assetid: f259d55b-dec7-4bde-8cf9-14521e4fdc42
ms.openlocfilehash: bc1241307e143a2de81cc99e6a934c83dcf89d23
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195391"
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
