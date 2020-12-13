---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2289'
title: Derleyici hatası C2289
ms.date: 11/04/2016
f1_keywords:
- C2289
helpviewer_keywords:
- C2289
ms.assetid: cb41a29e-1b06-47dc-bfce-8d73bd63a0df
ms.openlocfilehash: ba9af908af6defaccd6825ce3dad412ad6914c77
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185966"
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
