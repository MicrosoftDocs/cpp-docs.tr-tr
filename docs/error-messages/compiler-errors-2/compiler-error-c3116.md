---
title: Derleyici Hatası C3116
ms.date: 11/04/2016
f1_keywords:
- C3116
helpviewer_keywords:
- C3116
ms.assetid: 597463e1-a5cc-4ed3-a917-eae9a61d3312
ms.openlocfilehash: 3f587bc677d64bda0fb5eea0b7ebc8d5761a2e75
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50612029"
---
# <a name="compiler-error-c3116"></a>Derleyici Hatası C3116

'depolama tanımlayıcısı': arabirim yöntemi için geçersiz depolama sınıfı

Kullanılan `typedef`, `register`, veya `static` arabirim yöntemi için depolama sınıfı olarak. Bu depolama sınıfları arabirim üyeleri üzerinde izin verilmez.

Aşağıdaki örnek, C3116 oluşturur:

```
// C3116.cpp
__interface ImyInterface
{
   static void myFunc();   // C3116
};
```