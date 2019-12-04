---
title: Derleyici hatası C2474
ms.date: 11/04/2016
f1_keywords:
- C2474
helpviewer_keywords:
- C2474
ms.assetid: 64e6c61e-6e77-480e-bcf0-b30a2fc482ac
ms.openlocfilehash: ed2ba0d80ffcf2ef83abd551026bc6df4939ffbd
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74743737"
---
# <a name="compiler-error-c2474"></a>Derleyici hatası C2474

' anahtar sözcüğü ': bitişik noktalı virgül eksik, anahtar sözcük veya tanımlayıcı olabilir.

Derleyicinin noktalı virgül bulması bekleniyordu ve amacınızı belirleyemedi. Bu hatayı çözmek için noktalı virgül ekleyin.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2474 oluşturur.

```cpp
// C2474.cpp
// compile with: /clr /c

ref class A {
   ref class B {}
   property int i;   // C2474 error
};

// OK
ref class B {
   ref class D {};
   property int i;
};

ref class E {
   ref class F {} property;
   int i;
};
```
