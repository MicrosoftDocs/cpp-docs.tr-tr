---
title: Derleyici Hatası C3653 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3653
dev_langs:
- C++
helpviewer_keywords:
- C3653
ms.assetid: 316549d7-f7ef-4578-a2ba-57adc8aac527
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8d0409317cb0cdf6a248554cba2e18d7f9d2e0e0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46019009"
---
# <a name="compiler-error-c3653"></a>Derleyici Hatası C3653

'function': adlandırılmış bir geçersiz kılma olarak kullanılamaz: bulunamadı; kılınan bir işlev kullanarak işlevi açıkça adlandırmayı unuttunuz bir:: işleci?

Açık bir geçersiz kılma herhangi bir arabirimde bulunamadı bir işlev belirtildi. Daha fazla bilgi için [açık geçersiz kılmalar](../../windows/explicit-overrides-cpp-component-extensions.md).

Aşağıdaki örnek, C3653 oluşturur:

```
// C3653.cpp
// compile with: /clr
public interface struct I {
   void h();
};

public ref struct X : public I {
   virtual void f() new sealed = J {};   // C3653 no J in scope
   virtual void g() {}   // OK
   virtual void h() new sealed = I::h {};   // OK
};
```