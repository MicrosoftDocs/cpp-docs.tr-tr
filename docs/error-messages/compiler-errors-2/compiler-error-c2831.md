---
title: Derleyici hatası C2831
ms.date: 11/04/2016
f1_keywords:
- C2831
helpviewer_keywords:
- C2831
ms.assetid: c8c04288-0889-4265-a077-17f94cbcdcc9
ms.openlocfilehash: d2fa97e4b293d306a7d6ceecd08256c8212f8cb7
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74736899"
---
# <a name="compiler-error-c2831"></a>Derleyici hatası C2831

' işleç işleci ' Varsayılan parametrelere sahip olamaz

Yalnızca üç operatör Varsayılan parametrelere sahip olabilir:

- [new](../../cpp/new-operator-cpp.md)

- Atama =

- Sol parantez (

Aşağıdaki örnek C2831 oluşturur:

```cpp
// C2831.cpp
// compile with: /c
#define BINOP <=
class A {
public:
   int i;
   int operator BINOP(int x = 1) {   // C2831
   // try the following line instead
   // int operator BINOP(int x) {
      return i+x;
   }
};
```
