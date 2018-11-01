---
title: Derleyici Hatası C3798
ms.date: 11/04/2016
f1_keywords:
- C3798
helpviewer_keywords:
- C3798
ms.assetid: b2f8b1d8-8812-49b8-a346-28e48f02ba5c
ms.openlocfilehash: 52900a662211609e1e7adeb7cb493cf2d72ab846
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50548271"
---
# <a name="compiler-error-c3798"></a>Derleyici Hatası C3798

'belirticisi': özellik bildiriminde (yöntemler yerine alma/ayarlama özelliği yerleştirilmelidir) geçersiz kılma belirticisi olamaz

Bir özellik yanlış olarak bildirildi. Daha fazla bilgi için bkz.

- [property](../../windows/property-cpp-component-extensions.md)

- [abstract](../../windows/abstract-cpp-component-extensions.md)

- [sealed](../../windows/sealed-cpp-component-extensions.md)

## <a name="example"></a>Örnek

Aşağıdaki örnek C3798 oluşturur

```
// C3798.cpp
// compile with: /clr /c
ref struct A {
   property int Prop_1 abstract;   // C3798
   property int Prop_2 sealed;   // C3798

   // OK
   property int Prop_3 {
      virtual int get() abstract;
      virtual void set(int i) abstract;
   }

   property int Prop_4 {
      virtual int get() sealed;
      virtual void set(int i) sealed;
   }
};
```