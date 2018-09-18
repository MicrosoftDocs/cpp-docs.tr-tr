---
title: Derleyici Hatası C2460 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2460
dev_langs:
- C++
helpviewer_keywords:
- C2460
ms.assetid: d969fca9-3ac5-4e4e-88fc-df05510e2093
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cb2d85ffbc7aa799f0688fbb10021a04ef9455ad
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46022627"
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