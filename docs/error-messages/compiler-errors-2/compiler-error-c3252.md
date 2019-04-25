---
title: Derleyici Hatası C3252
ms.date: 11/04/2016
f1_keywords:
- C3252
helpviewer_keywords:
- C3252
ms.assetid: aa9ad096-e9ac-41c7-8ad9-b966751c7c75
ms.openlocfilehash: ee9245fb8eb89b9234e76dc10304b1d05bc1fdcb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62164845"
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