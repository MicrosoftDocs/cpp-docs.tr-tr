---
title: Derleyici Uyarısı (düzey 1) C4114
ms.date: 11/04/2016
f1_keywords:
- C4114
helpviewer_keywords:
- C4114
ms.assetid: 3983e1c6-e8bb-46dc-8894-e1827db48797
ms.openlocfilehash: 41e951e7c4a8b23ddbec14c5421f66702e70c937
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62300264"
---
# <a name="compiler-warning-level-1-c4114"></a>Derleyici Uyarısı (düzey 1) C4114

aynı tür niteleyicisi birden fazla kez kullanıldı

Tür niteleyicisine türü bildirim veya tanım kullanır (**const**, **geçici**, **imzalı**, veya **işaretsiz**) birden çok kez. Bu, bir uyarı ile Microsoft Uzatmaları (/Ze) ve ANSI uyumluluğu (/Za) altında bir hata neden olur.

Aşağıdaki örnek, C4114 oluşturur:

```
// C4114.cpp
// compile with: /W1 /c
volatile volatile int i;   // C4114
```

Aşağıdaki örnek, C4114 oluşturur:

```
// C4114_b.cpp
// compile with: /W1 /c
static const int const * ii;   // C4114
static const int * const iii;   // OK
```
