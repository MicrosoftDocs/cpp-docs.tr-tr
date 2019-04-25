---
title: Derleyici Uyarısı C4485
ms.date: 11/04/2016
f1_keywords:
- C4485
helpviewer_keywords:
- C4485
ms.assetid: a6f2b437-ca93-4dcd-b9cb-df415e10df86
ms.openlocfilehash: b5afb829485e0e9533a14e818e6d6785f268a83b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62311334"
---
# <a name="compiler-warning-c4485"></a>Derleyici Uyarısı C4485

'override_function': taban başvuru sınıfı yöntemiyle 'base_class_function' eşleşiyor, ancak işaretlenen 'new' veya 'override'; 'new' (ve 'virtual') varsayıldı

Erişimci, ile veya olmadan geçersiz kılmalar `virtual` anahtar sözcüğü, bir temel sınıf erişimci işlevi ancak `override` veya `new` tanımlayıcısı geçersiz kılma işlevi imzasının bir parçası değildi. Ekleme `new` veya `override` bu uyarıyı çözmek için tanımlayıcısı.

Bkz: [geçersiz kılma](../../extensions/override-cpp-component-extensions.md) ve [yeni (vtable'da yeni yuva)](../../extensions/new-new-slot-in-vtable-cpp-component-extensions.md) daha fazla bilgi için.

C4485 her zaman hata olarak verilir. Kullanım [uyarı](../../preprocessor/warning.md) C4485 bastırmak için pragması.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4485 oluşturur

```
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