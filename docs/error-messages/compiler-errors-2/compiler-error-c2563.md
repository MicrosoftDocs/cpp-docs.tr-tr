---
title: Derleyici Hatası C2563
ms.date: 11/04/2016
f1_keywords:
- C2563
helpviewer_keywords:
- C2563
ms.assetid: 54abba68-6458-4ca5-894d-3babdb7b3552
ms.openlocfilehash: 04a10c82fa6aa39bcf1098d6d4aabfc2f769e7c8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50539314"
---
# <a name="compiler-error-c2563"></a>Derleyici Hatası C2563

biçimsel parametre listesinde uyuşmazlık

Bir işlev (veya bir işlev işaretçisi) biçimsel parametre listesi başka bir işlev (ya da bir üye işlevi işaretçisi) eşleşmiyor. Sonuç olarak, işlevlerin veya işaretçiler atama yapılamıyor.

Aşağıdaki örnek, C2563 oluşturur:

```
// C2563.cpp
void func( int );
void func( int, int );
int main() {
   void *fp();
   fp = func;   // C2563
}
```