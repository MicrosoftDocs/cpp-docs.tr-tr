---
title: Derleyici Hatası C3900 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3900
dev_langs:
- C++
helpviewer_keywords:
- C3900
ms.assetid: a94cc561-8fa8-4344-9e01-e81ff462fae5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dfbec5086cd034b56795f47504c029e975aa36b4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46039679"
---
# <a name="compiler-error-c3900"></a>Derleyici Hatası C3900

'member': geçerli kapsamda izin verilmiyor

İşlev bildirimleri ve yalnızca satır içi işlev tanımları, özellik blok içerebilir. Üye işlevleri dışındaki özellik bloklarında izin verilir. Hiçbir tür tanımları, işleçler ve arkadaş işlevleri izin verilir. Daha fazla bilgi için [özelliği](../../windows/property-cpp-component-extensions.md).

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