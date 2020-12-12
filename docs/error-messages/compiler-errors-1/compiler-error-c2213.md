---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2213'
title: Derleyici hatası C2213
ms.date: 11/04/2016
f1_keywords:
- C2213
helpviewer_keywords:
- C2213
ms.assetid: ff012278-7f3b-4d49-aaed-2349756f6225
ms.openlocfilehash: aa9274f77c2416af286c306f2e6302b5f416a24b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245596"
---
# <a name="compiler-error-c2213"></a>Derleyici hatası C2213

' değiştirici ': __based için geçersiz bağımsız değişken

Değiştirme bağımsız değişkeni **`__based`** geçersiz.

Aşağıdaki örnek C2213 oluşturur:

```cpp
// C2213.cpp
// compile with: /c
int i;
int *j;
char __based(i) *p;   // C2213
char __based(j) *p2;   // OK
```
