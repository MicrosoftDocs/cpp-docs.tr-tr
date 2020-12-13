---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2460'
title: Derleyici hatası C2460
ms.date: 11/04/2016
f1_keywords:
- C2460
helpviewer_keywords:
- C2460
ms.assetid: d969fca9-3ac5-4e4e-88fc-df05510e2093
ms.openlocfilehash: 6a6b521b356d4005906e97b085271369f2624c46
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341860"
---
# <a name="compiler-error-c2460"></a>Derleyici hatası C2460

' Identifier1 ': tanımlanmakta olan ' identifier2 ' kullanır

Bir sınıf veya yapı ( `identifier2` ) kendisinin () üyesi olarak belirtilir `identifier1` . Sınıfların ve yapıların özyinelemeli tanımlarına izin verilmez.

Aşağıdaki örnek C2460 oluşturur:

```cpp
// C2460.cpp
class C {
   C aC;    // C2460
};
```

Bunun yerine, sınıfında bir işaretçi başvurusu kullanın.

```cpp
// C2460.cpp
class C {
   C * aC;    // OK
};
```
