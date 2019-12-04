---
title: Derleyici hatası C2289
ms.date: 11/04/2016
f1_keywords:
- C2289
helpviewer_keywords:
- C2289
ms.assetid: cb41a29e-1b06-47dc-bfce-8d73bd63a0df
ms.openlocfilehash: 32afd6b99b84fba1ef9c2c701306abc67488337c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759132"
---
# <a name="compiler-error-c2289"></a>Derleyici hatası C2289

aynı tür niteleyicisi birden fazla kez kullanıldı

Bir tür bildirimi veya tanımı birden çok kez bir tür niteleyicisi (`const`, `volatile`, `signed`veya `unsigned`) kullanır ve ANSI uyumluluğu ( **/za**) altında hataya neden olur.

Aşağıdaki örnek C2286 oluşturur:

```cpp
// C2289.cpp
// compile with: /Za /c
volatile volatile int i;   // C2289
volatile int j;   // OK
```
