---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2014'
title: Derleyici hatası C2014
ms.date: 11/04/2016
f1_keywords:
- C2014
helpviewer_keywords:
- C2014
ms.assetid: 231d8e9c-48c0-4027-99a3-245d186275ec
ms.openlocfilehash: 2f8de1d2b9ea8ef680826cfbfc189dbe2617c9f6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220987"
---
# <a name="compiler-error-c2014"></a>Derleyici hatası C2014

önişlemci komutu ilk boşluk olmayan bir başlangıç olmalıdır

`#`Önişlemci yönergesinin işareti, boşluk olmayan bir satırdaki ilk karakter olmalıdır.

Aşağıdaki örnek C2014 oluşturur:

```cpp
// C2014.cpp
int k; #include <stdio.h>   // C2014
```

Olası çözüm:

```cpp
// C2014b.cpp
// compile with: /c
int k;
#include <stdio.h>
```
