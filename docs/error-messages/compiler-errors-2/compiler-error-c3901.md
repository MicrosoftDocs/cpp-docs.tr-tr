---
title: Derleyici hatası C3901
ms.date: 11/04/2016
f1_keywords:
- C3901
helpviewer_keywords:
- C3901
ms.assetid: 19af4141-39ad-4c16-a68f-3ae76f648186
ms.openlocfilehash: 43dc5e6e4e515bf5fea867ee61de00f98a60a602
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74749093"
---
# <a name="compiler-error-c3901"></a>Derleyici hatası C3901

' accessor_function ': dönüş türü ' Type ' olmalıdır

En az bir get yönteminin dönüş türü Özellik türüyle eşleşmelidir. Daha fazla bilgi için bkz. [özellik](../../extensions/property-cpp-component-extensions.md).

Aşağıdaki örnek C3901 oluşturur:

```cpp
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
