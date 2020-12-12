---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2479'
title: Derleyici hatası C2479
ms.date: 11/04/2016
f1_keywords:
- C2479
helpviewer_keywords:
- C2479
ms.assetid: c74c7869-e65b-4ca1-b6fa-eb39fed4458a
ms.openlocfilehash: 7193112ee546b7314075b105cb88c68fce71a256
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123948"
---
# <a name="compiler-error-c2479"></a>Derleyici hatası C2479

' Identifier ': ' allocate () ' yalnızca statik kapsamın veri öğeleri için geçerlidir

`__declspec( allocate())`Söz dizimi yalnızca statik veriler için kullanılabilir.

Aşağıdaki örnek C2479 oluşturur:

```cpp
// C2479.cpp
// compile with: /c
#pragma section("mycode", read)
static __declspec(allocate("mycode")) void DoNothing() {}   // C2479
__declspec(allocate("mycode"))  int i = 0;   // OK
```
