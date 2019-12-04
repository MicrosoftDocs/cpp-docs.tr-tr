---
title: Derleyici hatası C2460
ms.date: 11/04/2016
f1_keywords:
- C2460
helpviewer_keywords:
- C2460
ms.assetid: d969fca9-3ac5-4e4e-88fc-df05510e2093
ms.openlocfilehash: a7d20a7658a75a492e19b9e81acaa3b6fce5cae7
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74743945"
---
# <a name="compiler-error-c2460"></a>Derleyici hatası C2460

' Identifier1 ': tanımlanmakta olan ' identifier2 ' kullanır

Bir sınıf veya yapı (`identifier2`) kendisinin bir üyesi olarak (`identifier1`) olarak bildirilmiştir. Sınıfların ve yapıların özyinelemeli tanımlarına izin verilmez.

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
