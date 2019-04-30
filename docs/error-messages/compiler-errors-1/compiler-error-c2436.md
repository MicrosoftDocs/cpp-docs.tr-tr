---
title: Derleyici Hatası C2436
ms.date: 11/04/2016
f1_keywords:
- C2436
helpviewer_keywords:
- C2436
ms.assetid: ca4cc813-bc1d-4c0a-9a2c-3a5fe673d084
ms.openlocfilehash: 335d4a304e16814243894c9524a9e4a2a7356110
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62375112"
---
# <a name="compiler-error-c2436"></a>Derleyici Hatası C2436

'identifier': üye işlev veya iç içe geçmiş sınıf oluşturucu başlatıcı listesinde

Üye işlevleri veya yerel sınıf oluşturucu başlatıcı listesinde başlatılamaz.

Aşağıdaki örnek, C2436 oluşturur:

```
// C2436.cpp
struct S{
   int f();
   struct Inner{
      int i;
   };
   S():f(10), Inner(0){}   // C2436
};
```