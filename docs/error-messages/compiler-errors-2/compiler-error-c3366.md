---
title: Derleyici Hatası C3366
ms.date: 11/04/2016
f1_keywords:
- C3366
helpviewer_keywords:
- C3366
ms.assetid: efc55bcf-c16d-43c1-a36f-87a6165fa2a8
ms.openlocfilehash: 4d1cd510cda9957ced1d9dd5fd8fea267f39220d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50507776"
---
# <a name="compiler-error-c3366"></a>Derleyici Hatası C3366

'variable': statik veri üyeleri, yönetilen veya WinRTtypes sınıf tanımının içinde tanımlanmalıdır

Bir WinRT ya da .NET sınıf veya arabirim dışında sınıf veya arabirim tanımı statik üyesi başvuru çalışıldı.

Derleyici, tam sınıfının tanımı, (meta verileri tek seferde sonra yaymak üzere) bilmesi gerekir ve statik veri üyeleri sınıf içinde başlatılacak gerektirir.

Örneğin, aşağıdaki örnekte C3366 oluşturur ve bu sorunun nasıl gösterir:

```
// C3366.cpp
// compile with: /clr /c
ref class X {
   public:
   static int i;   // initialize i here to avoid C3366
};

int X::i = 5;      // C3366
```
