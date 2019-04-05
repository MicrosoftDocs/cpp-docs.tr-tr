---
title: Derleyici Hatası C3900
ms.date: 11/04/2016
f1_keywords:
- C3900
helpviewer_keywords:
- C3900
ms.assetid: a94cc561-8fa8-4344-9e01-e81ff462fae5
ms.openlocfilehash: 35df94ccfcd7942f9057cb37ceee349c09b80607
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58777421"
---
# <a name="compiler-error-c3900"></a>Derleyici Hatası C3900

'member': geçerli kapsamda izin verilmiyor

İşlev bildirimleri ve yalnızca satır içi işlev tanımları, özellik blok içerebilir. Üye işlevleri dışındaki özellik bloklarında izin verilir. Hiçbir tür tanımları, işleçler ve arkadaş işlevleri izin verilir. Daha fazla bilgi için [özelliği](../../extensions/property-cpp-component-extensions.md).

Olay tanımlarına yalnızca erişim yöntemleri ve işlevleri içerebilir.

Aşağıdaki örnek, C3900 oluşturur:

```
// C3900.cpp
// compile with: /clr
ref class X {
   property int P {
      void set(int);   // OK
      int i;   // C3900 variable declaration
   };
};
```

Aşağıdaki örnek, C3900 oluşturur:

```
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