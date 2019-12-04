---
title: Derleyici hatası C2014
ms.date: 11/04/2016
f1_keywords:
- C2014
helpviewer_keywords:
- C2014
ms.assetid: 231d8e9c-48c0-4027-99a3-245d186275ec
ms.openlocfilehash: 6c7e941970415c933b38f35b6c09247a3c0fd411
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757403"
---
# <a name="compiler-error-c2014"></a>Derleyici hatası C2014

önişlemci komutu ilk boşluk olmayan bir başlangıç olmalıdır

Önişlemci yönergesinin `#` işareti, boşluk olmayan bir satırdaki ilk karakter olmalıdır.

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
