---
title: Derleyici Hatası C3797
ms.date: 11/04/2016
f1_keywords:
- C3797
helpviewer_keywords:
- C3797
ms.assetid: ab27ff34-8c1d-4297-b004-9e39bd3a4f25
ms.openlocfilehash: 76206cdffce3f551ff472cbd83df486eb41ae80b
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58774834"
---
# <a name="compiler-error-c3797"></a>Derleyici Hatası C3797

'override': olay bildiriminde (yerleştirilmelidir üzerinde olay ekleme/kaldırma/başlatma yöntemlerine yerine) geçersiz kılma belirticisi olamaz

Önemsiz bir olay Önemsiz başka bir olay ile (bir olay açıkça tanımlanmış erişimci metotlarını olmadan) geçersiz kılamaz. Geçersiz kılma olay davranışını erişimcisinin işlevlerle tanımlamanız gerekir.

Daha fazla bilgi için [olay](../../extensions/event-cpp-component-extensions.md).

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