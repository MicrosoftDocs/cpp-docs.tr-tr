---
title: Derleyici Hatası C2511
ms.date: 11/04/2016
f1_keywords:
- C2511
helpviewer_keywords:
- C2511
ms.assetid: df999efe-fe2b-418b-bb55-4af6a0592631
ms.openlocfilehash: 9d9ba48b0607e7a30b8748d4e9ae4f7025f11dea
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50522999"
---
# <a name="compiler-error-c2511"></a>Derleyici Hatası C2511

'identifier': Aşırı yüklenen üye işlev 'sınıfında' bulunamadı

Herhangi bir sürümü işlevi, belirtilen parametrelerle bildirilir.  Olası nedenler:

1. Yanlış parametre işleve geçirildi.

1. Geçirilen parametreler yanlış sırada.

1. Parametre adları yanlış yazımını.

Aşağıdaki örnek, C2511 oluşturur:

```
// C2511.cpp
// compile with: /c
class C {
   int c_2;
   int Func(char *, char *);
};

int C::Func(char *, char *, int i) {   // C2511
// try the following line instead
// int C::Func(char *, char *) {
   return 0;
}
```