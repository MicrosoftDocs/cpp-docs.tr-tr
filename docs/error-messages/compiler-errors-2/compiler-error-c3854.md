---
title: Derleyici Hatası C3854 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3854
dev_langs:
- C++
helpviewer_keywords:
- C3854
ms.assetid: 32a9ead0-c6c7-485a-8802-c7b1fe921d3a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d94d2462662fd5f99e80ba205b8e2df41d7c716b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099557"
---
# <a name="compiler-error-c3854"></a>Derleyici Hatası C3854

'=' işaretinin solundaki ifade bir işlev olarak değerleniyor. (Bir işlevin bir l değeri değildir) bir işleve atama yapılamaz

Bir başvuru başlatılmasına olamaz. Bir işleve bir başvuru'başvurusunun kaldırılması atama yapılamaz, bir rvalue olduğunu bir işlev verir. Bu nedenle, bir işlev başvurusu yoluyla atayamazsınız.

Aşağıdaki örnek, C3854 oluşturur:

```
// C3854.cpp
int afunc(int i)
{
   return i;
}

typedef int (& rFunc_t)(int);
typedef int (* pFunc_t)(int);

int main()
{
   rFunc_t rf = afunc;   // OK binding a reference to function
   pFunc_t pf = &afunc;   // OK initializing a pointer to function

   *pf = &afunc;   // C3854
   // try the following line instead
   // pf = &afunc;
   *rf = &afunc;   // C3854
}
```