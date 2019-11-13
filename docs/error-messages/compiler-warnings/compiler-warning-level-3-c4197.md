---
title: Derleyici Uyarısı (düzey 3) C4197
ms.date: 11/04/2016
f1_keywords:
- C4197
helpviewer_keywords:
- C4197
ms.assetid: f766feef-82b0-4d81-8a65-33628c7db196
ms.openlocfilehash: d7c8cee42f17ad3301980852b8333ea37f5ca6be
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051777"
---
# <a name="compiler-warning-level-3-c4197"></a>Derleyici Uyarısı (düzey 3) C4197

' Type ': tür dönüştürmedeki en üst düzey geçici değer yoksayıldı

Derleyici, [geçici](../../cpp/volatile-cpp.md)ile nitelenmiş bir r-value türüne bir tür dönüştürme algıladı ya da bir r-değer türü, geçici ile nitelenen bir türe dönüştürüldü. C standardına (6.5.3) göre, nitelikli türlerle ilişkili özellikler yalnızca l-Value ifadeleri için anlamlıdır.

Aşağıdaki örnek C4197 oluşturur:

```cpp
// C4197.cpp
// compile with: /W3
#include <stdio.h>
#include <signal.h>
#include <stdlib.h>

void sigproc(int);
struct S
{
   int i;
} s;

int main()
{
   signal(SIGINT, sigproc);
   s.i = 1;
   S *pS = &s;
   for ( ; (volatile int)pS->i ; )   // C4197
      break;
   // for ( ; *(volatile int *)&pS->i ; )   // OK
   //    break;
}

void sigproc(int) // ctrl-C
{
   signal(SIGINT, sigproc);
   s.i = 0;
}
```