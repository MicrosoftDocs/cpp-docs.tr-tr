---
title: Derleyici Hatası C2193
ms.date: 11/04/2016
f1_keywords:
- C2193
helpviewer_keywords:
- C2193
ms.assetid: 9813e853-d581-4f51-bb75-4e242298a844
ms.openlocfilehash: 1eb1145b7927733ab82253632847da90542250fd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62302624"
---
# <a name="compiler-error-c2193"></a>Derleyici Hatası C2193

'identifier': kesimde zaten var

Bir işlevi kullanarak iki farklı segmentler yerleştirildiği `alloc_text` ve `code_seg` pragmaları.

Aşağıdaki örnek, C2193 oluşturur:

```
// C2193.cpp
// compile with: /c
extern "C" void MYFUNCTION();
#pragma alloc_text(MYCODE, MYFUNCTION)
#pragma code_seg("MYCODE2")
extern "C" void MYFUNCTION() {}   // C2193
extern "C" void MYFUNCTION2() {}
```