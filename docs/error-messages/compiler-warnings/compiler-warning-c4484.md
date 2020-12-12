---
description: 'Hakkında daha fazla bilgi edinin: derleyici uyarısı C4484'
title: Derleyici Uyarısı C4484
ms.date: 11/04/2016
f1_keywords:
- C4484
helpviewer_keywords:
- C4484
ms.assetid: 3d30e5b3-2297-45b7-a37a-1360056fdd0e
ms.openlocfilehash: 43228cabc8dfd728ea104f6c3b57d863ec9e5e5a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97180740"
---
# <a name="compiler-warning-c4484"></a>Derleyici Uyarısı C4484

' override_function ': ' base_class_function ' temel başvuru sınıfı yöntemiyle eşleşiyor, ancak ' Virtual ', ' New ' veya ' override ' olarak işaretlenmemiş; ' New ' (' Virtual ' değil) varsayıldı

**/Clr** ile derlerken, derleyici bir temel sınıf işlevini örtülü olarak geçersiz kılmaz, bu da işlevin vtable 'da yeni bir yuva alabileceği anlamına gelir. Çözümlemek için, bir işlevin geçersiz kılma olup olmadığını açıkça belirtin.

Daha fazla bilgi için bkz:

- [/clr (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md)

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
