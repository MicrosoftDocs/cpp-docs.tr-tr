---
title: Derleyici Hatası C3290
ms.date: 11/04/2016
f1_keywords:
- C3290
helpviewer_keywords:
- C3290
ms.assetid: 0baf684b-1143-4953-ac99-a2fa267d8017
ms.openlocfilehash: f2a346354d8da7d78c5517b01b4438bfb8af50ad
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58774847"
---
# <a name="compiler-error-c3290"></a>Derleyici Hatası C3290

'type': Önemsiz bir özellik başvuru türüne sahip olamaz

Bir özellik yanlış olarak bildirildi. Önemsiz özellik bildirimini, derleyici özelliğini güncelleştirecek bir değişken oluşturur ve bir izleme başvurusu mümkün değil bir sınıftaki değişken.

Bkz: [özelliği](../../extensions/property-cpp-component-extensions.md) ve [Tracking Reference Operator](../../extensions/tracking-reference-operator-cpp-component-extensions.md) daha fazla bilgi için.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3290 oluşturur.

```
// C3290.cpp
// compile with: /clr /c
ref struct R {};

ref struct X {
   R^ mr;

   property R % y;   // C3290
   property R ^ x;   // OK

   // OK
   property R% prop {
      R% get() {
         return *mr;
      }

      void set(R%) {}
   }
};

int main() {
   X x;
   R% xp = x.prop;
}
```