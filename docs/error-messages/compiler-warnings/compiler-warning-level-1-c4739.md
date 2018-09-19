---
title: Derleyici Uyarısı (düzey 1) C4739 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4739
dev_langs:
- C++
helpviewer_keywords:
- C4739
ms.assetid: 600873b3-7c85-4cd4-944e-cd8e01bfcbb0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7beaaca5d5791079fd8ea1ff8764f0b721f8d57d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46112401"
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