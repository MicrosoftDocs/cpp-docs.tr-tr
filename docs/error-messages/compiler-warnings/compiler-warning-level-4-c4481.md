---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4481'
title: Derleyici Uyarısı (düzey 4) C4481
ms.date: 11/04/2016
f1_keywords:
- C4481
helpviewer_keywords:
- C4481
ms.assetid: 7bfd4e0c-b452-4e6c-b7c4-ac5cc93fe4ea
ms.openlocfilehash: 463df18090a4f6f632a80543576db4cb9048e754
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251303"
---
# <a name="compiler-warning-level-4-c4481"></a>Derleyici Uyarısı (düzey 4) C4481

Standart olmayan uzantı kullanıldı: geçersiz kılma belirticisi ' anahtar sözcüğü '

C++ standardında olmayan bir anahtar sözcük kullanıldı, örneğin,/CLRaltında de olan geçersiz kılma belirticilerden biri.  Daha fazla bilgi için bkz.,

- [/clr (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md)

- [Geçersiz kılma belirticileri](../../extensions/override-specifiers-cpp-component-extensions.md)

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
