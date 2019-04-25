---
title: Derleyici Hatası C2198
ms.date: 11/04/2016
f1_keywords:
- C2198
helpviewer_keywords:
- C2198
ms.assetid: 638a845c-9d7f-4115-a9aa-d72455605668
ms.openlocfilehash: a7fbc5dc6dc91dab5bfea3a81c8d5c045e485161
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182827"
---
# <a name="compiler-error-c2198"></a>Derleyici Hatası C2198

'function': çok az sayıda bağımsız değişken çağrısı için

Derleyici, işlev veya yanlış işlev bildirimi çağrısı için çok az sayıda parametre bulundu.

Aşağıdaki örnek, C2198 oluşturur:

```
// C2198.c
// compile with: /c
void func( int, int );
int main() {
   func( 1 );   // C2198 only one actual parameter
   func( 1, 1 );   // OK
}
```