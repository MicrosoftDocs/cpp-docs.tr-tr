---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3804'
title: Derleyici hatası C3804
ms.date: 11/04/2016
f1_keywords:
- C3804
helpviewer_keywords:
- C3804
ms.assetid: 7c4cda28-ec96-4d04-937b-36dbd9944722
ms.openlocfilehash: b033acefd9a583b1659755f63fdbd3781fc95ccd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291512"
---
# <a name="compiler-error-c3804"></a>Derleyici hatası C3804

' property_accessor ': bir özellik için erişimci metotları tüm statik veya statik olmayan bir şekilde olmalıdır

Önemsiz olmayan bir özellik tanımlarken, erişimci işlevleri statik veya örnek olabilir, ancak ikisi birden olamaz.

Daha fazla bilgi için bkz. [özelliği](../../extensions/property-cpp-component-extensions.md) .

## <a name="example"></a>Örnek

Aşağıdaki örnek C3804 oluşturur.

```cpp
// C3804.cpp
// compile with: /c /clr
ref struct A {

   property int i {
      static int get() {}
      void set(int i) {}
   }   // C3804 error

   // OK
   property int j {
      int get() { return 0; }
      void set(int i) {}
   }

   property int k {
      static int get() { return 0; }
      static void set(int i) {}
   }
};
```
