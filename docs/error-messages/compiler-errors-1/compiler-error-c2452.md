---
title: Derleyici Hatası C2452 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2452
dev_langs:
- C++
helpviewer_keywords:
- C2452
ms.assetid: a4ec7642-6660-4c7a-9866-853d1cc67daf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9c8785a8ce77849805d9620b412493accd8b8690
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46087012"
---
# <a name="compiler-error-c2452"></a>Derleyici Hatası C2452

'type': safe_cast için geçersiz kaynak türü

Kaynak türü [safe_cast](../../windows/safe-cast-cpp-component-extensions.md) geçerli değildi.  Örneğin, tüm türlerin bir `safe_cast` işlemi CLR Türleri olması gerekir.

Aşağıdaki örnek, C2452 oluşturur:

```
// C2452.cpp
// compile with: /clr

struct A {};
struct B : public A {};

ref struct C {};
ref struct D : public C{};

int main() {
   A a;
   safe_cast<B*>(&a);   // C2452

   // OK
   C ^ c = gcnew C;
   safe_cast<D^>(c);
}
```