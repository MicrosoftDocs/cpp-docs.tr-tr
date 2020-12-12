---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2652'
title: Derleyici hatası C2652
ms.date: 11/04/2016
f1_keywords:
- C2652
helpviewer_keywords:
- C2652
ms.assetid: 6e3d1a90-a989-4088-8afd-dc82f6a2d66f
ms.openlocfilehash: 6d0f85a089c527ce299e007ce04d96ac68daaf56
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286182"
---
# <a name="compiler-error-c2652"></a>Derleyici hatası C2652

' tanımlayıcı ': geçersiz kopya Oluşturucusu: ilk parametre bir ' Identifier ' olmamalıdır

Kopya oluşturucudaki ilk parametre, tanımlandığı sınıf, yapı veya birleşim ile aynı türde. İlk parametre türe bir başvuru olabilir, ancak türün kendisi olamaz.

Aşağıdaki örnek C2651 oluşturur:

```cpp
// C2652.cpp
// compile with: /c
class A {
   A( A );   // C2652 takes an A
};
class B {
   B( B& );   // OK, reference to B
};
```
