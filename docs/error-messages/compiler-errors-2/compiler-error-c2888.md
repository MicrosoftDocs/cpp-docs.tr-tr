---
title: Derleyici Hatası C2888 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2888
dev_langs:
- C++
helpviewer_keywords:
- C2888
ms.assetid: 244f593e-ff25-4dad-b31f-84dafa3bc84a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3a80f99eb4fcf888462d1356d60cb4b22af0d0f8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46023130"
---
# <a name="compiler-error-c2888"></a>Derleyici Hatası C2888

'identifier': simge 'ad alanı' ad alanı içinde tanımlanamaz

Bir ad alanına ait bir sembol a kapsayan bir ad alanında tanımlanmış olması gerekir

Aşağıdaki örnek, C2888 oluşturur:

```
// C2888.cpp
// compile with: /c
namespace M {
   namespace N {
      void f1();
      void f2();
   }

   void N::f1() {}   // OK: namspace M encloses N
}

namespace O {
   void M::N::f2() {}   // C2888 namespace O does not enclose M
}
```