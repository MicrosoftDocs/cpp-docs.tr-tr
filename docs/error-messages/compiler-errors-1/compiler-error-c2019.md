---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2019'
title: Derleyici hatası C2019
ms.date: 11/04/2016
f1_keywords:
- C2019
helpviewer_keywords:
- C2019
ms.assetid: 4f37b1e1-9eca-418f-a4c3-141e8512d7b6
ms.openlocfilehash: 5b30bdb8eace513572152d0f33da5f591e21bd6e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97283933"
---
# <a name="compiler-error-c2019"></a>Derleyici hatası C2019

Önişlemci yönergesi bekleniyordu, ' character ' bulundu

Karakter bir işaret izler, `#` ancak bir Önişlemci yönergesinin ilk harfi değildir.

Aşağıdaki örnek C2019 oluşturur:

```cpp
// C2019.cpp
#!define TRUE 1   // C2019
```

Olası çözüm:

```cpp
// C2019b.cpp
// compile with: /c
#define TRUE 1
```
