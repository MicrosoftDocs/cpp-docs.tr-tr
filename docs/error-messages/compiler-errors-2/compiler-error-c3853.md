---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3853'
title: Derleyici hatası C3853
ms.date: 11/04/2016
f1_keywords:
- C3853
helpviewer_keywords:
- C3853
ms.assetid: 5b71805d-52b4-44ec-80ae-37c68d876f6a
ms.openlocfilehash: c10306fd8626475a0ac3dbb7b9e14b7773e4157b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328194"
---
# <a name="compiler-error-c3853"></a>Derleyici hatası C3853

' = ': bir işlev başvurusu aracılığıyla bir başvuruyu veya atamayı yeniden başlatmak geçersizdir

İşlevler lvalues olmadığından, bir işlev aracılığıyla başvuruya atanamaz.

Aşağıdaki örnekler C3853 oluşturur:

```cpp
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
