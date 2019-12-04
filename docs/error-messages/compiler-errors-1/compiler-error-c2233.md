---
title: Derleyici hatası C2233
ms.date: 11/04/2016
f1_keywords:
- C2233
helpviewer_keywords:
- C2233
ms.assetid: 236bdf0b-9607-4f26-a249-d8def0b1333c
ms.openlocfilehash: 066f28bfaacd1ad2e7645822aef082e43e863327
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759262"
---
# <a name="compiler-error-c2233"></a>Derleyici hatası C2233

' tanımlayıcı ': Sıfır boyutlu diziler içeren nesne dizileri geçersizdir

Bir dizideki her nesnenin en az bir öğe içermesi gerekir.

Aşağıdaki örnek C2233 oluşturur:

```cpp
// C2233.cpp
// compile with: /c
class A {
   char somearray[1];
};

class B {
   char zeroarray[];
};

A array[100];   // OK
B array2[100];   // C2233
```
