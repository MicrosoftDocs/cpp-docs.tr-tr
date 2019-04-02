---
title: Derleyici Uyarısı (düzey 4) C4481
ms.date: 11/04/2016
f1_keywords:
- C4481
helpviewer_keywords:
- C4481
ms.assetid: 7bfd4e0c-b452-4e6c-b7c4-ac5cc93fe4ea
ms.openlocfilehash: fe96ff50f4081e3c9dbe3c7eb68da156a69c96ab
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58776374"
---
# <a name="compiler-warning-level-4-c4481"></a>Derleyici Uyarısı (düzey 4) C4481

Standart olmayan uzantı kullanıldı: geçersiz kılma belirticisi 'anahtar sözcüğü'

Bir anahtar sözcüğü C++ standardı, örneğin, bir/CLR altında da çalışır geçersiz kılma tanımlayıcılarını olmadığını kullanıldı.  Daha fazla bilgi için bkz:

- [/clr (Ortak Dil Çalışma Zamanı Derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md)

- [Geçersiz kılma tanımlayıcıları](../../extensions/override-specifiers-cpp-component-extensions.md)

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4481 oluşturur.

```
// C4481.cpp
// compile with: /W4 /c
class B {
   virtual void f(unsigned);
};

class C : B {
   void f(unsigned) override;   // C4481
   void f2(unsigned);
};
```