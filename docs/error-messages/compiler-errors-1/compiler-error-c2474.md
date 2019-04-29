---
title: Derleyici Hatası C2474
ms.date: 11/04/2016
f1_keywords:
- C2474
helpviewer_keywords:
- C2474
ms.assetid: 64e6c61e-6e77-480e-bcf0-b30a2fc482ac
ms.openlocfilehash: c49f38b828a41c72135ba9182d4d0f5eee4df1de
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62350890"
---
# <a name="compiler-error-c2474"></a>Derleyici Hatası C2474

'anahtar sözcüğü': bir hemen yanında noktalı virgül eksik olabilir anahtar sözcük ya da tanımlayıcı.

Derleyici, noktalı virgül bekleniyordu ve amacınızla belirleyemedi. Bu hatayı gidermek için noktalı virgül ekleyin.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2474 oluşturur.

```
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