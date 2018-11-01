---
title: Derleyici Hatası C2153
ms.date: 11/04/2016
f1_keywords:
- C2153
helpviewer_keywords:
- C2153
ms.assetid: cfc50cb7-9a0f-4b5b-879a-d419c99f7be1
ms.openlocfilehash: eeb7da509ffb1b8c408763c79d471586eb94f383
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50605939"
---
# <a name="compiler-error-c2153"></a>Derleyici Hatası C2153

onaltılık sabitlerde en az bir onaltılık basamak olmalıdır

Onaltılık sabitler 0 x, 0 X ve \x geçerli değildir. En az bir onaltılık basamak izlemelidir x ya da X.

Aşağıdaki örnek, C2153 oluşturur:

```
// C2153.cpp
int main() {
   int a= 0x;    // C2153
   int b= 0xA;   // OK
}
```