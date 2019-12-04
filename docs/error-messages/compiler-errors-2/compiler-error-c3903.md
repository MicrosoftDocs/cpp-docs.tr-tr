---
title: Derleyici hatası C3903
ms.date: 11/04/2016
f1_keywords:
- C3903
helpviewer_keywords:
- C3903
ms.assetid: cf47d7ad-a3bd-4f75-a253-71586e7a3be6
ms.openlocfilehash: 585fb82c2838b2bc8aebbfbab7bdda744ba38da8
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74749080"
---
# <a name="compiler-error-c3903"></a>Derleyici hatası C3903

' Property ': set veya get yöntemi yok

Özelliğin en az bir `get` veya `set` yöntemi olmalıdır. Daha fazla bilgi için bkz. [özellik](../../extensions/property-cpp-component-extensions.md).

Aşağıdaki örnek C3903 oluşturur:

```cpp
// C3903.cpp
// compile with: /clr
ref class X {
   property int P {
      void f(int){}
      // Add one or both of the following lines.
      // void set(int){}
      // int get(){return 0;}
   };   // C3903

   property double Q[,,,,] {
      void f(){}
      // Add one or both of the following lines.
      // void set(int, char, int, char, double, double){}
      // double get(int, char, int, char, double){return 1.1;}
   }   // C3903
};
```
