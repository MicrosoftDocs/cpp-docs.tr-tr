---
title: Derleyici Uyarısı C4485
ms.date: 11/04/2016
f1_keywords:
- C4485
helpviewer_keywords:
- C4485
ms.assetid: a6f2b437-ca93-4dcd-b9cb-df415e10df86
ms.openlocfilehash: 896fca6c6b257c90ccdf813a9c6cb6bc27ad9e96
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73623619"
---
# <a name="compiler-warning-c4485"></a>Derleyici Uyarısı C4485

' override_function ': ' base_class_function ' taban başvuru sınıfı yöntemiyle eşleşiyor, ancak ' New ' veya ' override ' olarak işaretlenmemiş; ' New ' (ve ' Virtual ') varsayıldı

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