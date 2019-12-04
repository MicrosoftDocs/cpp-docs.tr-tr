---
title: Derleyici hatası C3900
ms.date: 11/04/2016
f1_keywords:
- C3900
helpviewer_keywords:
- C3900
ms.assetid: a94cc561-8fa8-4344-9e01-e81ff462fae5
ms.openlocfilehash: f1289fb9a4d60f2c75b54fd573c83064f1517282
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74749106"
---
# <a name="compiler-error-c3900"></a>Derleyici hatası C3900

' Member ': geçerli kapsamda izin verilmiyor

Özellik blokları yalnızca işlev bildirimleri ve satır içi işlev tanımları içerebilir. Özellik bloklarından işlevler dışında bir üyeye izin verilmez. Typedefs, Operators veya Friend işlevlerine izin verilmez. Daha fazla bilgi için bkz. [özellik](../../extensions/property-cpp-component-extensions.md).

Olay tanımları yalnızca erişim yöntemleri ve işlevleri içerebilir.

Aşağıdaki örnek C3900 oluşturur:

```cpp
// C3900.cpp
// compile with: /clr
ref class X {
   property int P {
      void set(int);   // OK
      int i;   // C3900 variable declaration
   };
};
```

Aşağıdaki örnek C3900 oluşturur:

```cpp
// C3900b.cpp
// compile with: /clr
using namespace System;
delegate void H();
ref class X {
   event H^ E {
      int m;   // C3900

      // OK
      void Test() {}

      void add( H^ h ) {}
      void remove( H^ h ) {}
      void raise( ) {}
   }
};
```
