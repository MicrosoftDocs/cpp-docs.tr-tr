---
title: Derleyici Hatası C3252 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3252
dev_langs:
- C++
helpviewer_keywords:
- C3252
ms.assetid: aa9ad096-e9ac-41c7-8ad9-b966751c7c75
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 70a38090bcbe1a984e643d6d995abe2c79339163
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46080629"
---
# <a name="compiler-error-c3252"></a>Derleyici Hatası C3252

'method': WinRT türü ya da yönetilen sanal yöntemin erişilebilirliği azaltılamaz

Bir temel sınıftan sanal bir yöntem veya bir arabirimden herhangi bir yöntemini uygulayan bir sınıf, yöntemin erişim indiremezsiniz.

Arabirim içindeki tüm yöntemleri ortak olduğunu unutmayın.

Aşağıdaki örnek, C3252 oluşturur ve bu sorunun nasıl gösterir:

```
// C3252.cpp
// compile with: /clr /c
ref class A {
public:
   virtual void f1() {}
};

ref class B : public A {
// To fix, uncomment the following line:
// public:
   virtual void f1() override sealed {}   // C3252, make this method public
};
```