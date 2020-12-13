---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3290'
title: Derleyici hatası C3290
ms.date: 11/04/2016
f1_keywords:
- C3290
helpviewer_keywords:
- C3290
ms.assetid: 0baf684b-1143-4953-ac99-a2fa267d8017
ms.openlocfilehash: 68c0e79c233f7fbd416f6bdbe42cc555c04731fa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337418"
---
# <a name="compiler-error-c3290"></a>Derleyici hatası C3290

' Type ': önemsiz bir özellik başvuru türüne sahip olamaz

Bir özellik yanlış bildirildi. Önemsiz bir özellik bildirdiğinizde, derleyici özelliğin güncelleşolacağı bir değişken oluşturur ve bir sınıfta izleme başvurusu değişkeni olması mümkün değildir.

Daha fazla bilgi için bkz. [özellik](../../extensions/property-cpp-component-extensions.md) ve [izleme başvurusu operatörü](../../extensions/tracking-reference-operator-cpp-component-extensions.md) .

## <a name="example"></a>Örnek

Aşağıdaki örnek C3290 oluşturur.

```cpp
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
