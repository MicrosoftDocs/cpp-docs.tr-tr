---
title: Derleyici Hatası C2106
ms.date: 11/04/2016
f1_keywords:
- C2106
helpviewer_keywords:
- C2106
ms.assetid: d5c91a2e-04e4-4770-8478-788b98c52a53
ms.openlocfilehash: 6a82792c8a8acfd0d397e02929a457aae8ef7050
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208938"
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