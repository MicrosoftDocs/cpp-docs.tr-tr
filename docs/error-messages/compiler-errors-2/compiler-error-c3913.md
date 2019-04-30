---
title: Derleyici Hatası C3913
ms.date: 11/04/2016
f1_keywords:
- C3913
helpviewer_keywords:
- C3913
ms.assetid: a678bfce-9524-470d-9f23-7d08ecb972c8
ms.openlocfilehash: 3a38f7bffd56f025510e092ad37b5f810cb11a9b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406567"
---
# <a name="compiler-error-c3913"></a>Derleyici Hatası C3913

Varsayılan özelliğin dizini oluşturulmalıdır

Varsayılan bir özelliği yanlış tanımlandı.

Daha fazla bilgi için [özelliği](../../extensions/property-cpp-component-extensions.md).

Aşağıdaki örnek, C3913 oluşturur:

```
// C3913.cpp
// compile with: /clr /c
ref struct X {
   property int default {   // C3913
   // try the following line instead
   // property int default[int] {
      int get(int) { return 0; }
      void set(int, int) {}
   }
};
```