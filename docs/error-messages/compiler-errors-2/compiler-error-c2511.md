---
title: Derleyici hatası C2511
ms.date: 11/04/2016
f1_keywords:
- C2511
helpviewer_keywords:
- C2511
ms.assetid: df999efe-fe2b-418b-bb55-4af6a0592631
ms.openlocfilehash: ff78cb50b274fe40d513739264bd7e9894bbed9d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74746571"
---
# <a name="compiler-error-c2511"></a>Derleyici hatası C2511

' tanımlayıcı ': aşırı yüklenmiş üye işlev ' class ' içinde bulunamadı

İşlevin hiçbir sürümü belirtilen parametrelerle bildirilmemiş.  Olası nedenler:

1. İşleve yanlış parametreler geçirildi.

1. Parametreler yanlış sırada geçirildi.

1. Parametre adlarının yanlış yazımı.

Aşağıdaki örnek C2511 oluşturur:

```cpp
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
