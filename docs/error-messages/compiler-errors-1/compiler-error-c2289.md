---
title: Derleyici hatası C2289
ms.date: 11/04/2016
f1_keywords:
- C2289
helpviewer_keywords:
- C2289
ms.assetid: cb41a29e-1b06-47dc-bfce-8d73bd63a0df
ms.openlocfilehash: 239552eb383197e57fcc6285cbf416c7c71c858b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216277"
---
# <a name="compiler-error-c2289"></a>Derleyici hatası C2289

aynı tür niteleyicisi birden fazla kez kullanıldı

Bir tür bildirimi veya tanımı birden çok kez bir tür niteleyicisi ( **`const`** ,, **`volatile`** **`signed`** veya **`unsigned`** ) kullanır ve ANSI uyumluluğu (**/za**) altında hataya neden olur.

Aşağıdaki örnek C2286 oluşturur:

```cpp
// C2289.cpp
// compile with: /Za /c
volatile volatile int i;   // C2289
volatile int j;   // OK
```
