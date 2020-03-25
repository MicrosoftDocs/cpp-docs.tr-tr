---
title: Derleyici Uyarısı (düzey 1) C4441
ms.date: 11/04/2016
f1_keywords:
- C4441
helpviewer_keywords:
- C4441
ms.assetid: 7fc540a5-e41f-47cf-aa37-b2b699c2685e
ms.openlocfilehash: 4de80a9b7ad5601d9f8760d7c55a64a8631307a8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80162380"
---
# <a name="compiler-warning-level-1-c4441"></a>Derleyici Uyarısı (düzey 1) C4441

' CC1 ' çağırma kuralı yoksayıldı; Bunun yerine ' CC2 ' kullanıldı

Yönetilen Kullanıcı tanımlı türler ve genel işlev genel türlerindeki üye işlevleri [__clrcall](../../cpp/clrcall.md) çağırma kuralını kullanmalıdır.  `__clrcall`kullanılan derleyici.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4441 oluşturur.

```cpp
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
