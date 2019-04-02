---
title: Derleyici Hatası C3901
ms.date: 11/04/2016
f1_keywords:
- C3901
helpviewer_keywords:
- C3901
ms.assetid: 19af4141-39ad-4c16-a68f-3ae76f648186
ms.openlocfilehash: 31fbb1e89a0619b4dc8b3f6c86f7f6bc748b80d6
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58780125"
---
# <a name="compiler-error-c3901"></a>Derleyici Hatası C3901

'accessor_function': dönüş türü 'type' olmalıdır

En az bir get metodun dönüş türü Özellik türüyle eşleşmelidir. Daha fazla bilgi için [özelliği](../../extensions/property-cpp-component-extensions.md).

Aşağıdaki örnek, C3901 oluşturur:

```
// C3901.cpp
// compile with: /clr /c
using namespace System;
ref class X {
   property String^ Name {
      void get();   // C3901
      // try the following line instead
      // String^ get();
   };
};

ref class Y {
   property double values[int, int] {
      int get(int, int);   // C3901
      // try the following line instead
      // double get(int, int);
   };
};
```