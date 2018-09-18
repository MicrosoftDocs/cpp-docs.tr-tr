---
title: Derleyici Uyarısı (düzey 4) C4481 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4481
dev_langs:
- C++
helpviewer_keywords:
- C4481
ms.assetid: 7bfd4e0c-b452-4e6c-b7c4-ac5cc93fe4ea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 48ed2ba08423f7540f4e0a855aacbcab993d41aa
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46063768"
---
# <a name="compiler-warning-level-4-c4481"></a>Derleyici Uyarısı (düzey 4) C4481

Standart olmayan uzantı kullanıldı: geçersiz kılma belirticisi 'anahtar sözcüğü'

Bir anahtar sözcüğü C++ standardı, örneğin, bir/CLR altında da çalışır geçersiz kılma tanımlayıcılarını olmadığını kullanıldı.  Daha fazla bilgi için bkz:

- [/clr (Ortak Dil Çalışma Zamanı Derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md)

- [Geçersiz kılma tanımlayıcıları](../../windows/override-specifiers-cpp-component-extensions.md)

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