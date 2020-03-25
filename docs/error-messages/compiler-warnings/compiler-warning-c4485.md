---
title: Derleyici Uyarısı C4485
ms.date: 11/04/2016
f1_keywords:
- C4485
helpviewer_keywords:
- C4485
ms.assetid: a6f2b437-ca93-4dcd-b9cb-df415e10df86
ms.openlocfilehash: c92f805eb2960336ed34f5da93b6c13f46bf15ac
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165151"
---
# <a name="compiler-warning-c4485"></a>Derleyici Uyarısı C4485

' override_function ': ' base_class_function ' temel başvuru sınıfı yöntemiyle eşleşiyor, ancak ' New ' veya ' override ' olarak işaretlenmemiş; ' New ' (ve ' Virtual ') varsayıldı

Bir erişimci, bir temel sınıf erişimci işlevi olan `virtual` anahtar sözcüğüyle veya olmadan geçersiz kılar, ancak `override` veya `new` belirticisi geçersiz kılma işlevi imzasının bir parçası değildi. Bu uyarıyı çözmek için `new` veya `override` belirticisi ekleyin.

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
