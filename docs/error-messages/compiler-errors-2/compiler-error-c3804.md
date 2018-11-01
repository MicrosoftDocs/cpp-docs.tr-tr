---
title: Derleyici Hatası C3804
ms.date: 11/04/2016
f1_keywords:
- C3804
helpviewer_keywords:
- C3804
ms.assetid: 7c4cda28-ec96-4d04-937b-36dbd9944722
ms.openlocfilehash: e83380696aca3d6d45c235925b830bef9e3061a3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50544592"
---
# <a name="compiler-error-c3804"></a>Derleyici Hatası C3804

'property_accessor': erişimci metotlarını bir özelliğin tamamı statik veya statik.

Önemsiz bir özelliğin tanımlarken, ya da statik erişimci işlevleri olabilir veya örneği, ikisini birden belirtmeyin.

Bkz: [özelliği](../../windows/property-cpp-component-extensions.md) daha fazla bilgi için.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3804 oluşturur.

```
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