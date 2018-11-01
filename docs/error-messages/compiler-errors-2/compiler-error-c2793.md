---
title: Derleyici Hatası C2793
ms.date: 11/04/2016
f1_keywords:
- C2793
helpviewer_keywords:
- C2793
ms.assetid: ce35f4e8-c357-40ca-95c4-15ff001ad69d
ms.openlocfilehash: 5533a0e8f75a1a513fbabe451fb41629a4595382
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428190"
---
# <a name="compiler-error-c2793"></a>Derleyici Hatası C2793

'token': arkasında beklenmeyen belirteç '::', tanımlayıcısı veya beklenen'operator ' anahtar sözcüğü

İzleyebileceğiniz yalnızca belirteçleri `__super::` tanımlayıcı veya anahtar sözcüğü `operator`.

Aşağıdaki örnek C2793 oluşturur

```
// C2793.cpp
struct B {
   void mf();
};

struct D : B {
   void mf() {
      __super::(); // C2793
   }
};
```