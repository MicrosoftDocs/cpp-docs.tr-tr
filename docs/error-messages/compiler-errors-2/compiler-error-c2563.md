---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2563'
title: Derleyici hatası C2563
ms.date: 11/04/2016
f1_keywords:
- C2563
helpviewer_keywords:
- C2563
ms.assetid: 54abba68-6458-4ca5-894d-3babdb7b3552
ms.openlocfilehash: 2243e0820b2e69d6bc05351fdba4600188a3ac08
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209158"
---
# <a name="compiler-error-c2563"></a>Derleyici hatası C2563

biçimsel parametre listesinde uyuşmazlık

Bir işlevin (veya bir işlev işaretçisinin) biçimsel parametre listesi, başka bir işlevden (veya bir üye işlev işaretçisinden) eşleşmiyor. Sonuç olarak, işlev veya işaretçilerin atanması yapılamaz.

Aşağıdaki örnek C2563 oluşturur:

```cpp
// C2563.cpp
void func( int );
void func( int, int );
int main() {
   void *fp();
   fp = func;   // C2563
}
```
