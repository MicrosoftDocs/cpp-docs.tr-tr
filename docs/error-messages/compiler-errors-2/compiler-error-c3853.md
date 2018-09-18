---
title: Derleyici Hatası C3853 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3853
dev_langs:
- C++
helpviewer_keywords:
- C3853
ms.assetid: 5b71805d-52b4-44ec-80ae-37c68d876f6a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a347321b8c7884381fc57412d18422d7993d2f22
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46021635"
---
# <a name="compiler-error-c3853"></a>Derleyici Hatası C3853

'=': bir başvurusu veya bir başvuru işlev aracılığıyla atamayı yeniden başlatmak geçersizdir

Bir işlev aracılığıyla bir başvuru işlevleri lvalues olmadığından atayamazsınız.

Aşağıdaki örnekler C3853 oluştur:

```
// C3853.cpp
// compile with: /EHsc
#include <iostream>
int afunc(int i)
{
   return i;
}

typedef int (& rFunc_t)(int);

int main()
{
   rFunc_t rf = afunc;   // OK binding a reference to function
   rf = afunc;   // C3853, can't reassign to a ref that's an lvalue
   int i = 99;
   int & ri = i;
   std::cout << i << std::endl;
   ri = 0;   // OK, i = 88;
   std::cout << i << std::endl;
}
```