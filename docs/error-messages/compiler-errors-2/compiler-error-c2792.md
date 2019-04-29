---
title: Derleyici Hatası C2792
ms.date: 11/04/2016
f1_keywords:
- C2792
helpviewer_keywords:
- C2792
ms.assetid: 392cf748-4f5e-4e62-a364-3118d5658408
ms.openlocfilehash: 40047cb557fba49f94e5c4e42f172cbcd999c65a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62360183"
---
# <a name="compiler-error-c2792"></a>Derleyici Hatası C2792

'super': Bu anahtar sözcük gelmelidir '::'

Anahtar sözcüğünü izleyen yalnızca belirteç `__super` olduğu `::`.

Aşağıdaki örnek, C2792 oluşturur:

```
// C2792.cpp
struct B {
   void mf();
};

struct D : B {
   void mf() {
      __super.();   // C2792

      // try the following line instead
      // __super::mf();
   }
};
```