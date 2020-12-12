---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3252'
title: Derleyici hatası C3252
ms.date: 11/04/2016
f1_keywords:
- C3252
helpviewer_keywords:
- C3252
ms.assetid: aa9ad096-e9ac-41c7-8ad9-b966751c7c75
ms.openlocfilehash: 59b5a0073d3dc8147b2e89d637fd98ba7339f6b8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194312"
---
# <a name="compiler-error-c3252"></a>Derleyici hatası C3252

' Method ': yönetilen veya WinRT türündeki bir sanal metodun erişilebilirliği azaltılamaz

Bir taban sınıftan veya bir arabirimden herhangi bir yöntemden sanal bir yöntemi uygulayan bir sınıf, bu yöntemin erişimini azaltamaz.

Bir arabirimdeki tüm yöntemlerin genel olduğunu unutmayın.

Aşağıdaki örnek C3252 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
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
