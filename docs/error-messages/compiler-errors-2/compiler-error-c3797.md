---
title: Derleyici Hatası C3797
ms.date: 11/04/2016
f1_keywords:
- C3797
helpviewer_keywords:
- C3797
ms.assetid: ab27ff34-8c1d-4297-b004-9e39bd3a4f25
ms.openlocfilehash: 2c8570edf16b9c002f9506b1b179a2ab36f7f26e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50557540"
---
# <a name="compiler-error-c3797"></a>Derleyici Hatası C3797

'override': olay bildiriminde (yerleştirilmelidir üzerinde olay ekleme/kaldırma/başlatma yöntemlerine yerine) geçersiz kılma belirticisi olamaz

Önemsiz bir olay Önemsiz başka bir olay ile (bir olay açıkça tanımlanmış erişimci metotlarını olmadan) geçersiz kılamaz. Geçersiz kılma olay davranışını erişimcisinin işlevlerle tanımlamanız gerekir.

Daha fazla bilgi için [olay](../../windows/event-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3797 oluşturur.

```
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