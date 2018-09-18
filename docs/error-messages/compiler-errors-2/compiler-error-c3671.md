---
title: Derleyici Hatası C3671 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3671
dev_langs:
- C++
helpviewer_keywords:
- C3671
ms.assetid: d684e4ae-87e2-4424-80bb-6f346652c831
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 455b9e2a6accbc98ee8bce49a35a672d9cd9c20d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46017081"
---
# <a name="compiler-error-c3671"></a>Derleyici Hatası C3671

'function_1': işlev 'function_2' Kılmıyor

Bir işlev değil kılınırsa açık geçersiz kılma sözdizimi kullanıldığında, derleyici bir hata oluşturur.  Bkz: [açık geçersiz kılmalar](../../windows/explicit-overrides-cpp-component-extensions.md) daha fazla bilgi için.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3671 oluşturur.

```
// C3671.cpp
// compile with: /clr /c
ref struct S {
   virtual void f();
};

ref struct S1 : S {
   virtual void f(int) new sealed = S::f;   // C3671
   virtual void f() new sealed = S::f;
};
```