---
title: Derleyici Hatası C2511 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2511
dev_langs:
- C++
helpviewer_keywords:
- C2511
ms.assetid: df999efe-fe2b-418b-bb55-4af6a0592631
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b628adda383baee0f2ec03ace715d94c6cca764c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46058152"
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