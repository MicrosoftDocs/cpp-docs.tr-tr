---
title: Derleyici Uyarısı (düzey 4) C4481
ms.date: 11/04/2016
f1_keywords:
- C4481
helpviewer_keywords:
- C4481
ms.assetid: 7bfd4e0c-b452-4e6c-b7c4-ac5cc93fe4ea
ms.openlocfilehash: fb51d16cc15c244b31d65f7777de66c372bbde33
ms.sourcegitcommit: d0504e2337bb671e78ec6dd1c7b05d89e7adf6a7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2019
ms.locfileid: "74683200"
---
# <a name="compiler-warning-level-4-c4481"></a>Derleyici Uyarısı (düzey 4) C4481

Standart olmayan uzantı kullanıldı: geçersiz kılma belirticisi ' anahtar sözcüğü '

C++ Standart olmayan bir anahtar sözcük kullanıldı, örneğin,/CLRaltında da çalıştığı geçersiz kılma belirticilerden biri.  Daha fazla bilgi için bkz.,

- [/clr (Ortak Dil Çalışma Zamanı Derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md)

- [Geçersiz Kılma Tanımlayıcıları](../../extensions/override-specifiers-cpp-component-extensions.md)

## <a name="example"></a>Örnek

Aşağıdaki örnek C4481 oluşturur.

```cpp
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