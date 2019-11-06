---
title: Derleyici Uyarısı C4484
ms.date: 11/04/2016
f1_keywords:
- C4484
helpviewer_keywords:
- C4484
ms.assetid: 3d30e5b3-2297-45b7-a37a-1360056fdd0e
ms.openlocfilehash: 4d3f72ddf7675ea7ad73022dc55a60fdc74d4390
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73623625"
---
# <a name="compiler-warning-c4484"></a>Derleyici Uyarısı C4484

' override_function ': ' base_class_function ' taban başvuru sınıfı yöntemiyle eşleşiyor, ancak ' Virtual ', ' New ' veya ' override ' olarak işaretlenmemiş; ' New ' (' Virtual ' değil) varsayıldı

**/Clr**ile derlerken, derleyici bir temel sınıf işlevini örtülü olarak geçersiz kılmaz, bu da işlevin vtable 'da yeni bir yuva alabileceği anlamına gelir. Çözümlemek için, bir işlevin geçersiz kılma olup olmadığını açıkça belirtin.

Daha fazla bilgi için bkz.:

- [/clr (Ortak Dil Çalışma Zamanı Derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md)

- [override](../../extensions/override-cpp-component-extensions.md)

- [yeni (vtable'de yeni yuva)](../../extensions/new-new-slot-in-vtable-cpp-component-extensions.md)

C4484 her zaman bir hata olarak verilir. C4484 bastırmak için [Warning](../../preprocessor/warning.md) pragma kullanın.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4484 oluşturur.

```cpp
// C4484.cpp
// compile with: /clr
ref struct A {
   virtual void Test() {}
};

ref struct B : A {
   void Test() {}   // C4484
};

// OK
ref struct C {
   virtual void Test() {}
   virtual void Test2() {}
};

ref struct D : C {
   virtual void Test() new {}
   virtual void Test2() override {}
};
```