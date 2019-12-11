---
title: Derleyici Uyarısı (düzey 4) C4481
ms.date: 11/04/2016
f1_keywords:
- C4481
helpviewer_keywords:
- C4481
ms.assetid: 7bfd4e0c-b452-4e6c-b7c4-ac5cc93fe4ea
ms.openlocfilehash: 853720b1c2476d9d8012916d42fe31dc884b16a7
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74990789"
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
