---
title: Derleyici Hatası C2101
ms.date: 11/04/2016
f1_keywords:
- C2101
helpviewer_keywords:
- C2101
ms.assetid: 42f0136f-8cc1-4f2b-be1c-721ec9278e66
ms.openlocfilehash: 68fa83f3325a2a7b91d32495aa9b6924e5ca8c0f
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344940"
---
# <a name="compiler-error-c2101"></a>Derleyici Hatası C2101

' &' üzerinde sabiti

Address-of işlecini ( `&` ) olarak işlenen bir l değeri olmalıdır.

Aşağıdaki örnek, C2101 oluşturur:

```
// C2101.cpp
int main() {
   char test;
   test = &'a';   // C2101
   test = 'a';   // OK
}
```