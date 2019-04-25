---
title: Derleyici Hatası C2289
ms.date: 11/04/2016
f1_keywords:
- C2289
helpviewer_keywords:
- C2289
ms.assetid: cb41a29e-1b06-47dc-bfce-8d73bd63a0df
ms.openlocfilehash: 9fe9b765af72a8864e3e899cafcf648a9facb67e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182801"
---
# <a name="compiler-error-c2289"></a>Derleyici Hatası C2289

aynı tür niteleyicisi birden fazla kez kullanıldı

Tür niteleyicisine türü bildirim veya tanım kullanır (`const`, `volatile`, `signed`, veya `unsigned`) birden çok kez, ANSI Uyumluluğu altında bir hata neden (**/Za**).

Aşağıdaki örnek, C2286 oluşturur:

```
// C2289.cpp
// compile with: /Za /c
volatile volatile int i;   // C2289
volatile int j;   // OK
```