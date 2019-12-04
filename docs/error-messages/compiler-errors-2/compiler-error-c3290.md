---
title: Derleyici hatası C3290
ms.date: 11/04/2016
f1_keywords:
- C3290
helpviewer_keywords:
- C3290
ms.assetid: 0baf684b-1143-4953-ac99-a2fa267d8017
ms.openlocfilehash: a7a73c13c28923761674294d8d6e601b95ffad96
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760159"
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
