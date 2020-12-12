---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4114'
title: Derleyici Uyarısı (düzey 1) C4114
ms.date: 11/04/2016
f1_keywords:
- C4114
helpviewer_keywords:
- C4114
ms.assetid: 3983e1c6-e8bb-46dc-8894-e1827db48797
ms.openlocfilehash: 7d1d7696fabdf8e5114ba733f7bf6de53353bcb4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97267449"
---
# <a name="compiler-warning-level-1-c4114"></a>Derleyici Uyarısı (düzey 1) C4114

aynı tür niteleyicisi birden fazla kez kullanıldı

Bir tür bildirimi veya tanımı bir tür niteleyicisi ( **`const`** ,, **`volatile`** **`signed`** veya) birden **`unsigned`** çok kez kullanır. Bu, Microsoft uzantıları (/Ze) ile bir uyarı ve ANSI uyumluluğu (/Za) altında bir hata oluşmasına neden olur.

Aşağıdaki örnek C4114 oluşturur:

```cpp
// C4114.cpp
// compile with: /W1 /c
volatile volatile int i;   // C4114
```

Aşağıdaki örnek C4114 oluşturur:

```cpp
// C4114_b.cpp
// compile with: /W1 /c
static const int const * ii;   // C4114
static const int * const iii;   // OK
```
