---
title: Derleyici Uyarısı (düzey 1) C4722
ms.date: 11/04/2016
f1_keywords:
- C4722
helpviewer_keywords:
- C4722
ms.assetid: d8660710-f67b-4f59-a5fd-59259475529e
ms.openlocfilehash: 320061c2daf2be042afe45828af637638399beaf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62327294"
---
# <a name="compiler-warning-level-1-c4722"></a>Derleyici Uyarısı (düzey 1) C4722

'function': yok edici hiç dönmüyor, olası bellek sızıntısı

Denetim akışı bir yok edici içinde sonlandırır. İş parçacığı veya tüm program sona erer ve ayrılan kaynakları serbest.  Ayrıca, özel durum işleme sırasında yığın geriye doğru izleme için bir yok Edicisi çağrılır, yürütülebilir dosyanın davranış tanımlanmamıştır.

Çözümlemek için yok edici değil döndürmek neden işlev çağrısı kaldırın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4722 oluşturur:

```
// C4722.cpp
// compile with: /O1 /W1 /c
#include <stdlib.h>
class C {
public:
   C();
   ~C() { exit(1); };   // C4722
};

extern void func (C*);

void Test(){
   C x;
   func(&x);
   // control will not leave Test because destructor will exit
}
```