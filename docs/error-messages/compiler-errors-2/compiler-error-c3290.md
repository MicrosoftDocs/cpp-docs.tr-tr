---
title: Derleyici Hatası C3290
ms.date: 11/04/2016
f1_keywords:
- C3290
helpviewer_keywords:
- C3290
ms.assetid: 0baf684b-1143-4953-ac99-a2fa267d8017
ms.openlocfilehash: d82d3272563f7a5af5de399a2f7fff621500e612
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50490487"
---
# <a name="compiler-error-c3290"></a>Derleyici Hatası C3290

'type': Önemsiz bir özellik başvuru türüne sahip olamaz

Bir özellik yanlış olarak bildirildi. Önemsiz özellik bildirimini, derleyici özelliğini güncelleştirecek bir değişken oluşturur ve bir izleme başvurusu mümkün değil bir sınıftaki değişken.

Bkz: [özelliği](../../windows/property-cpp-component-extensions.md) ve [Tracking Reference Operator](../../windows/tracking-reference-operator-cpp-component-extensions.md) daha fazla bilgi için.

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