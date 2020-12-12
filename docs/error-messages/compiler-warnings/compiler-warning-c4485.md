---
description: 'Hakkında daha fazla bilgi edinin: derleyici uyarısı C4485'
title: Derleyici Uyarısı C4485
ms.date: 11/04/2016
f1_keywords:
- C4485
helpviewer_keywords:
- C4485
ms.assetid: a6f2b437-ca93-4dcd-b9cb-df415e10df86
ms.openlocfilehash: 85ce885aa299adf68b12d46f0a74af5aa55319f1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97180714"
---
# <a name="compiler-warning-c4485"></a>Derleyici Uyarısı C4485

' override_function ': ' base_class_function ' temel başvuru sınıfı yöntemiyle eşleşiyor, ancak ' New ' veya ' override ' olarak işaretlenmemiş; ' New ' (ve ' Virtual ') varsayıldı

Bir erişimci, **`virtual`** bir temel sınıf erişimci işlevi olan anahtar sözcüğüyle veya olmadan geçersiz kılar, ancak `override` veya **`new`** belirticisi geçersiz kılma işlevi imzasının bir parçası değildi. **`new`** `override` Bu uyarıyı çözmek için veya tanımlayıcısını ekleyin.

Daha fazla bilgi için bkz. [geçersiz kılma](../../extensions/override-cpp-component-extensions.md) ve [Yeni (vtable 'da yeni yuva)](../../extensions/new-new-slot-in-vtable-cpp-component-extensions.md) .

C4485 her zaman bir hata olarak verilir. C4485 bastırmak için [Warning](../../preprocessor/warning.md) pragma kullanın.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4485 oluşturur

```cpp
// C4485.cpp
// compile with: /clr
delegate void Del();

ref struct A {
   virtual event Del ^E;
};

ref struct B : A {
   virtual event Del ^E;   // C4485
};

ref struct C : B {
   virtual event Del ^E {
      void raise() override {}
      void add(Del ^) override {}
      void remove(Del^) override {}
   }
};
```
