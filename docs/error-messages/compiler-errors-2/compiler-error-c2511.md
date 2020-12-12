---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2511'
title: Derleyici hatası C2511
ms.date: 11/04/2016
f1_keywords:
- C2511
helpviewer_keywords:
- C2511
ms.assetid: df999efe-fe2b-418b-bb55-4af6a0592631
ms.openlocfilehash: 846173cc887fd09b564d18e063820bc0e0d5b184
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97212928"
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
