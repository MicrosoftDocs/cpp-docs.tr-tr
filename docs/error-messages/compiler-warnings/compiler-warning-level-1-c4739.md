---
title: Derleyici Uyarısı (düzey 1) C4739
ms.date: 11/04/2016
f1_keywords:
- C4739
helpviewer_keywords:
- C4739
ms.assetid: 600873b3-7c85-4cd4-944e-cd8e01bfcbb0
ms.openlocfilehash: 4c48ad9349361324c18ec790c51d1095cce104e2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62280444"
---
# <a name="compiler-warning-level-1-c4739"></a>Derleyici Uyarısı (düzey 1) C4739

'var' değişkeni başvuru depolama alanını aşıyor

Bir değişkene bir değer Atandı ancak değişkenin boyutundan daha büyük bir değerdir. Bellek değişkenin bellek konumuna yazılır ve veri kaybı mümkündür.

Bu uyarıyı çözmek için yalnızca bir değer boyutu değeri barındırabilecek bir değişkene atayın.

Aşağıdaki örnek, C4739 oluşturur:

```
// C4739.cpp
// compile with: /RTCs /Zi /W1 /c
char *pc;
int main() {
   char c;
   *(int *)&c = 1;   // C4739

   // OK
   *(char *)&c = 1;
}
```