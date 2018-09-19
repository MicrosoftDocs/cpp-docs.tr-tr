---
title: Derleyici Uyarısı (düzey 1) C4441 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4441
dev_langs:
- C++
helpviewer_keywords:
- C4441
ms.assetid: 7fc540a5-e41f-47cf-aa37-b2b699c2685e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a505c47ea348175a16c91c309646428f1222d091
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46033439"
---
# <a name="compiler-warning-level-1-c4441"></a>Derleyici Uyarısı (düzey 1) C4441

çağırma kuralı yoksayıldı; 'cc1' Bunun yerine 'cc2'

Yönetilen kullanıcı tanımlı türler ve genel işlev genel türler, üye işlevleri kullanmalıdır [__clrcall](../../cpp/clrcall.md) çağırma kuralı.  Kullanılan derleyici `__clrcall`.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4441 oluşturur.

```
// C4441.cpp
// compile with: /clr /W1 /c
generic <class ItemType>
void __cdecl Test(ItemType item) {}   // C4441
// try the following line instead
// void Test(ItemType item) {}

ref struct MyStruct {
   void __cdecl Test(){}   // C4441
   void Test2(){}   // OK
};
```