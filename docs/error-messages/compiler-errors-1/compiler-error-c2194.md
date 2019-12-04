---
title: Derleyici hatası C2194
ms.date: 11/04/2016
f1_keywords:
- C2194
helpviewer_keywords:
- C2194
ms.assetid: df6e631c-0062-4844-9088-4cc7a0ff879f
ms.openlocfilehash: 7d7c1324ea295752a09cf9c87ef37164ab6a06db
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758547"
---
# <a name="compiler-error-c2194"></a>Derleyici hatası C2194

' tanımlayıcı ': bir metin segmenti

`data_seg` pragma `code_seg`ile kullanılan bir segment adı kullanır.

Aşağıdaki örnek C2194 oluşturur:

```cpp
// C2194.cpp
// compile with: /c
#pragma code_seg("MYCODE")
#pragma data_seg("MYCODE")   // C2194
#pragma data_seg("MYCODE2")   // OK
```
