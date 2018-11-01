---
title: Derleyici Hatası C2652
ms.date: 11/04/2016
f1_keywords:
- C2652
helpviewer_keywords:
- C2652
ms.assetid: 6e3d1a90-a989-4088-8afd-dc82f6a2d66f
ms.openlocfilehash: 9c9772052b690ad87de1d408c06478d82d48e724
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50464811"
---
# <a name="compiler-error-c2652"></a>Derleyici Hatası C2652

'identifier': Geçersiz kopya Oluşturucusu: ilk parametre bir 'identifier' olmalıdır

Kopya Oluşturucu ilk parametre bir sınıf, yapı veya birleşim kendisi için tanımlanan aynı türde sahiptir. İlk parametre türü ancak türün kendisine bir başvuru olabilir.

Aşağıdaki örnek, C2651 oluşturur:

```
// C2652.cpp
// compile with: /c
class A {
   A( A );   // C2652 takes an A
};
class B {
   B( B& );   // OK, reference to B
};
```