---
title: Derleyici Hatası C3766 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3766
dev_langs:
- C++
helpviewer_keywords:
- C3766
ms.assetid: b5af2089-2e1e-4e45-a41d-495b6c55656e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d96fa83f072d0c0b86854400753f0b798ac73d14
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46094688"
---
# <a name="compiler-error-c3766"></a>Derleyici Hatası C3766

'type' yöntemi 'function' arabirimi için bir uygulama sağlamalıdır

Bir arabirimden devralan bir sınıf, arabirim üyeleri uygulamalıdır.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3766 oluşturur.

```
// C3766.cpp
// compile with: /clr /c

delegate void MyDel();

interface struct IFace {
   virtual event MyDel ^ E;
};

ref struct Class1 : public IFace {};   // C3766

// OK
ref struct Class2 : public IFace {
   virtual event MyDel ^ E {
      void add(MyDel ^) {}
      void remove(MyDel ^) {}
   }
};
```