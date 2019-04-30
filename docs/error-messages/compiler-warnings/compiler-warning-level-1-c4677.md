---
title: Derleyici Uyarısı (düzey 1) C4677
ms.date: 11/04/2016
f1_keywords:
- C4677
helpviewer_keywords:
- C4677
ms.assetid: a8d656a1-e2ff-4f8b-9028-201765131026
ms.openlocfilehash: 66b8d42b63bcbf328703523c4eeda7a047f4643c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62374579"
---
# <a name="compiler-warning-level-1-c4677"></a>Derleyici Uyarısı (düzey 1) C4677

'function': özel üyenin olmayan imzası 'private_type' derleme özel türünü içeriyor

Genel erişilebilirlik derlemenin dışında olan bir türü derleme dışından özel erişimi olan bir türü kullanır. Genel bütünleştirilmiş kod türe başvuran bir bileşen türü üyesi veya derleme özel türünü başvuran üyeleri kullanmanız mümkün olmayacaktır.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4677 oluşturur.

```
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