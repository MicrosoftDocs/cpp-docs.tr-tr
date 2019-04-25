---
title: Derleyici Uyarısı (düzey 1) C4549
ms.date: 11/04/2016
f1_keywords:
- C4549
helpviewer_keywords:
- C4549
ms.assetid: 81a07676-625b-4f58-9b0c-3ee22830b04a
ms.openlocfilehash: 5732b2f963be52512d5d80f2552af4a80acb3372
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62226579"
---
# <a name="compiler-warning-level-1-c4549"></a>Derleyici Uyarısı (düzey 1) C4549

'operator': virgülden önceki etkisi yok; işleci 'operator' kullanmak mı istiyordunuz?

Derleyici, bir virgül yapılı ifade algıladı.

Varsayılan olarak bu uyarıyı kapalıdır. Daha fazla bilgi için [derleyici uyarıları emin olan kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

Aşağıdaki örnek, C4549 oluşturur:

```
// C4549.cpp
// compile with: /W1
#pragma warning (default : 4549)

int main() {
   int i = 0, k = 0;

   if ( i == 0, k )   // C4549
   // try the following line instead
   // if ( i == 0 )
      i++;
}
```