---
title: Derleyici Uyarısı (düzey 1) C4722 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4722
dev_langs:
- C++
helpviewer_keywords:
- C4722
ms.assetid: d8660710-f67b-4f59-a5fd-59259475529e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0f450120ff05c7e13888bf4b4ce4425405525b4c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46112505"
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