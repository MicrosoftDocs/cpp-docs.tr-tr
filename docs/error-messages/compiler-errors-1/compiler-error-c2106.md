---
title: Derleyici Hatası C2106
ms.date: 11/04/2016
f1_keywords:
- C2106
helpviewer_keywords:
- C2106
ms.assetid: d5c91a2e-04e4-4770-8478-788b98c52a53
ms.openlocfilehash: 6a82792c8a8acfd0d397e02929a457aae8ef7050
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50507581"
---
# <a name="compiler-error-c2106"></a>Derleyici Hatası C2106

'operator': sol işlenen l değeri olmalıdır

İşlecinin sol işleneni bir l değeri olmalıdır.

Aşağıdaki örnek, C2106 oluşturur:

```
// C2106.cpp
int main() {
   int a;
   1 = a;   // C2106
   a = 1;   // OK
}
```