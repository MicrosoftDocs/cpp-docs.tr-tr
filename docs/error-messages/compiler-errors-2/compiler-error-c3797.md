---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3797'
title: Derleyici hatası C3797
ms.date: 11/04/2016
f1_keywords:
- C3797
helpviewer_keywords:
- C3797
ms.assetid: ab27ff34-8c1d-4297-b004-9e39bd3a4f25
ms.openlocfilehash: 581dae7ba2649d72fc2670b99c9255b3ee9f7838
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97244868"
---
# <a name="compiler-error-c3797"></a>Derleyici hatası C3797

' override ': olay bildiriminde geçersiz kılma belirticisi olamaz (Bunun yerine olay ekleme/kaldırma/yükseltme yöntemlerine yerleştirilmelidir)

Önemsiz bir olayı (açıkça tanımlanmış erişimci yöntemleri olmayan bir olay) başka bir önemsiz olayla birlikte geçersiz kılamazsınız. Geçersiz kılma olayı, davranışını erişimci işlevleriyle tanımlamalıdır.

Daha fazla bilgi için bkz. [olay](../../extensions/event-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3797 oluşturur.

```cpp
// C3797.cpp
// compile with: /clr /c
delegate void MyDel();

ref class Class1 {
public:
   virtual event MyDel ^ E;
};

ref class Class2 : public Class1 {
public:
   virtual event MyDel ^ E override;   // C3797
};

// OK
ref class Class3 : public Class1 {
public:
   virtual event MyDel ^ E {
      void add(MyDel ^ d) override {}
      void remove(MyDel ^ d) override {}
   }
};
```
