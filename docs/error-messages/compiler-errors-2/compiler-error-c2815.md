---
title: Derleyici hatası C2815
ms.date: 11/04/2016
f1_keywords:
- C2815
helpviewer_keywords:
- C2815
ms.assetid: d0256fd6-0721-4c99-b03c-52d96e77a613
ms.openlocfilehash: 579fc94f3b16056b5f26dd0b9ea16b5fc36fda22
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74750721"
---
# <a name="compiler-error-c2815"></a>Derleyici hatası C2815

' operator delete ': ilk biçimsel parametre ' void * ' olmalıdır, ancak ' param ' kullanıldı

Kullanıcı tanımlı [işleç silme](../../standard-library/new-operators.md#op_delete) işlevinin, `void *`türünde bir ilk biçimsel parametre olması gerekir.

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
