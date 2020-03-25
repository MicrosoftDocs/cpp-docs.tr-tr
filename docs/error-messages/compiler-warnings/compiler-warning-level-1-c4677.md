---
title: Derleyici Uyarısı (düzey 1) C4677
ms.date: 11/04/2016
f1_keywords:
- C4677
helpviewer_keywords:
- C4677
ms.assetid: a8d656a1-e2ff-4f8b-9028-201765131026
ms.openlocfilehash: 5b31fd22c917b2c0f505ca189425f8160f62f748
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175551"
---
# <a name="compiler-warning-level-1-c4677"></a>Derleyici Uyarısı (düzey 1) C4677

' function ': özel olmayan üyenin imzası ' private_type ' derleme özel türünü içeriyor

Derleme dışında genel erişilebilirlik içeren bir tür, derlemenin dışında özel erişimi olan bir tür kullanır. Ortak derleme türüne başvuran bir bileşen, tür üyesini veya derleme özel türüne başvuran üyeleri kullanamaz.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4677 oluşturur.

```cpp
// C4677.cpp
// compile with: /clr /c /W1
delegate void TestDel();
public delegate void TestDel2();

public ref class MyClass {
public:
   static event TestDel^ MyClass_Event;   // C4677
   static event TestDel2^ MyClass_Event2;   // OK
};
```
