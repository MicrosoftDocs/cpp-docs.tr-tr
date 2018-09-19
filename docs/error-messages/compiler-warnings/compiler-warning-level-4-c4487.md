---
title: Derleyici Uyarısı (düzey 4) C4487 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4487
dev_langs:
- C++
helpviewer_keywords:
- C4487
ms.assetid: 796144cf-cd3c-4edc-b6a4-96192b7eb4f0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ffc1a25d362cad95f2aad43d626e4918955903f5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46135847"
---
# <a name="compiler-warning-level-4-c4487"></a>Derleyici Uyarısı (düzey 4) C4487

'derived_class_function': 'base_class_function' devralınan sanal olmayan yöntemiyle eşleşiyor ancak açıkça 'new' işaretli değil

Türetilen bir sınıfta bir işleve, sanal olmayan temel sınıf işlevi aynı imzaya sahiptir. C4487 türetilmiş sınıf işlev temel sınıf işlevini geçersiz kılmaz anımsatır. Türetilmiş sınıf işlevi açıkça işaretleyin `new` bu uyarıyı çözmek için.

Daha fazla bilgi için [yeni (vtable'da yeni yuva)](../../windows/new-new-slot-in-vtable-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4487 oluşturur.

```
// C4487.cpp
// compile with: /W4 /clr
using namespace System;
public ref struct B {
   void f() { Console::WriteLine("in B::f"); }
   void g() { Console::WriteLine("in B::g"); }
};

public ref struct D : B {
   void f() { Console::WriteLine("in D::f"); }   // C4487
   void g() new { Console::WriteLine("in D::g"); }   // OK
};

int main() {
   B ^ a = gcnew D;
   // will call base class functions
   a->f();
   a->g();
}
```