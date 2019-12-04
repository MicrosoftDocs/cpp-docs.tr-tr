---
title: Derleyici hatası C2652
ms.date: 11/04/2016
f1_keywords:
- C2652
helpviewer_keywords:
- C2652
ms.assetid: 6e3d1a90-a989-4088-8afd-dc82f6a2d66f
ms.openlocfilehash: cedee3f1e3289aaf0ea38d75b6c812b61f891435
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756129"
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
