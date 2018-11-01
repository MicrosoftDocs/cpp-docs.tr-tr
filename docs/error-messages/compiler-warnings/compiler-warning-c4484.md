---
title: Derleyici Uyarısı C4484
ms.date: 11/04/2016
f1_keywords:
- C4484
helpviewer_keywords:
- C4484
ms.assetid: 3d30e5b3-2297-45b7-a37a-1360056fdd0e
ms.openlocfilehash: 71a3d903ba32fecac4b2d8bfc3e0a93f19d0f4ed
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50473183"
---
# <a name="compiler-warning-c4484"></a>Derleyici Uyarısı C4484

'override_function': taban başvuru sınıfı yöntemiyle 'base_class_function' eşleşiyor, ancak 'virtual', 'new' veya 'override'; işaretli değil 'new' (ve 'virtual' değil) varsayıldı

İle derlerken **/CLR**, derleyici işlev vtable'da yeni yuva alacak anlamına gelir. bir temel sınıf işlev örtük olarak geçersiz kılmaz. Çözümlemek için açıkça bir işlevi geçersiz kılma olup olmadığını belirtin.

Daha fazla bilgi için bkz.:

- [/clr (Ortak Dil Çalışma Zamanı Derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md)

- [override](../../windows/override-cpp-component-extensions.md)

- [Yeni (vtable'da yeni yuva)](../../windows/new-new-slot-in-vtable-cpp-component-extensions.md)

C4484 her zaman hata olarak verilir. Kullanım [uyarı](../../preprocessor/warning.md) C4484 bastırmak için pragması.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4484 oluşturur.

```
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