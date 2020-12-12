---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2815'
title: Derleyici hatası C2815
ms.date: 11/04/2016
f1_keywords:
- C2815
helpviewer_keywords:
- C2815
ms.assetid: d0256fd6-0721-4c99-b03c-52d96e77a613
ms.openlocfilehash: fd0ee162c10acd89e4746ea906d64ea8ef069271
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194845"
---
# <a name="compiler-error-c2815"></a>Derleyici hatası C2815

' operator delete ': ilk biçimsel parametre ' void * ' olmalıdır, ancak ' param ' kullanıldı

Kullanıcı tanımlı [işleç silme](../../standard-library/new-operators.md#op_delete) işlevi, türünde bir ilk biçimsel parametre almalıdır `void *` .

Aşağıdaki örnek C2815 oluşturur:

```cpp
// C2815.cpp
// compile with: /c
class CMyClass {
public:
   void mf1(int *a);
   void operator delete(CMyClass *);   // C2815
   void operator delete(void *);
};
```
