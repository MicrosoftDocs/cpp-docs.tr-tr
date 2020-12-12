---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4677'
title: Derleyici Uyarısı (düzey 1) C4677
ms.date: 11/04/2016
f1_keywords:
- C4677
helpviewer_keywords:
- C4677
ms.assetid: a8d656a1-e2ff-4f8b-9028-201765131026
ms.openlocfilehash: e2edd37149fd4242cc1a0f5c5df29fe4fe21e17f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97285428"
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
