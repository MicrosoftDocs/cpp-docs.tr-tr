---
title: Derleyici Hatası C2460
ms.date: 11/04/2016
f1_keywords:
- C2460
helpviewer_keywords:
- C2460
ms.assetid: d969fca9-3ac5-4e4e-88fc-df05510e2093
ms.openlocfilehash: 414b6e53cf1610a55db984a1127bfc884102494f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50589598"
---
# <a name="compiler-error-c2460"></a>Derleyici Hatası C2460

'ıdentifier1': 'anda tanımlanmakta olan kullanımlar identifier2',

Bir sınıf veya yapı (`identifier2`) kendisinin üyesi bildirilmiş (`identifier1`). Sınıfları ve yapıları özyinelemeli tanımlarını izin verilmez.

Aşağıdaki örnek, C2460 oluşturur:

```
// C2460.cpp
class C {
   C aC;    // C2460
};
```

Bunun yerine, bir işaretçi başvuru sınıfında kullanın.

```
// C2460.cpp
class C {
   C * aC;    // OK
};
```