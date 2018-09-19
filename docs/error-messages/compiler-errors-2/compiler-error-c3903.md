---
title: Derleyici Hatası C3903 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3903
dev_langs:
- C++
helpviewer_keywords:
- C3903
ms.assetid: cf47d7ad-a3bd-4f75-a253-71586e7a3be6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dcdeb10df07abcab34afddc7b852f75a2180bf2e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46086485"
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