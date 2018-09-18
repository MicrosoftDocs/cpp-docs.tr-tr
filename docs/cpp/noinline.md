---
title: noinline | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- noinline_cpp
dev_langs:
- C++
helpviewer_keywords:
- noinline __declspec keyword
- __declspec keyword [C++], noinline
ms.assetid: f259d55b-dec7-4bde-8cf9-14521e4fdc42
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c7a2831251d00f0dc24b1cfab7beeecaff100962
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46092296"
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

