---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2436'
title: Derleyici hatası C2436
ms.date: 11/04/2016
f1_keywords:
- C2436
helpviewer_keywords:
- C2436
ms.assetid: ca4cc813-bc1d-4c0a-9a2c-3a5fe673d084
ms.openlocfilehash: 3858146d48006c1129f6dca1992e229603b70a79
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97189918"
---
# <a name="compiler-error-c2436"></a>Derleyici hatası C2436

' tanımlayıcı ': Oluşturucu başlatıcı listesinde üye işlev veya iç içe sınıf

Oluşturucu başlatıcı listesindeki üye işlevleri veya yerel sınıflar başlatılamıyor.

Aşağıdaki örnek C2436 oluşturur:

```cpp
// C2436.cpp
struct S{
   int f();
   struct Inner{
      int i;
   };
   S():f(10), Inner(0){}   // C2436
};
```
