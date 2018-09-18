---
title: Derleyici Hatası C3651 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3651
dev_langs:
- C++
helpviewer_keywords:
- C3651
ms.assetid: a03e692e-c219-4654-9827-8415cfa5a22d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7cff220121be333b6df1bc802654f792e36acf17
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46017282"
---
# <a name="compiler-error-c3651"></a>Derleyici Hatası C3651

'member': açık bir geçersiz kılma kullanılamaz, bir taban sınıfının üyesi olmalıdır

Açık bir geçersiz kılma belirtildi, ancak geçersiz kılınmasını işlevi bir temel tür değil bir tür içinde.

Daha fazla bilgi için [açık geçersiz kılmalar](../../windows/explicit-overrides-cpp-component-extensions.md).

Aşağıdaki örnek, C3651 oluşturur:

```
// C3651.cpp
// compile with: /clr /c
ref class C {
public:
   virtual void func2();
};

ref class Other {
public:
   virtual void func();
};

ref class D : public C {
public:
   virtual void func() new sealed = Other::func;   // C3651
   virtual void func2() new sealed = C::func2;   // OK
};
```