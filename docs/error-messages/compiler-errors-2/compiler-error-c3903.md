---
title: Derleyici Hatası C3903
ms.date: 11/04/2016
f1_keywords:
- C3903
helpviewer_keywords:
- C3903
ms.assetid: cf47d7ad-a3bd-4f75-a253-71586e7a3be6
ms.openlocfilehash: 0d650d5c3a361ae91e9a35a39866d30bff93f5f9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50654200"
---
# <a name="compiler-error-c3903"></a>Derleyici Hatası C3903

'property': yok ayarladığınız veya alma yöntemine

Bir özellik en az bir sahip olmanız gerekir `get` veya `set` yöntemi. Daha fazla bilgi için [özelliği](../../windows/property-cpp-component-extensions.md).

Aşağıdaki örnek, C3903 oluşturur:

```
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