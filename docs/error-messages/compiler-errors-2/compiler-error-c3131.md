---
title: Derleyici Hatası C3131
ms.date: 11/04/2016
f1_keywords:
- C3131
helpviewer_keywords:
- C3131
ms.assetid: 38f20fac-83c9-4cd9-b7b5-74ca8f650ea6
ms.openlocfilehash: 082839c01a2da4b0d149962367b9719932d2b272
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50530893"
---
# <a name="compiler-error-c3131"></a>Derleyici Hatası C3131

Proje 'name' özelliğine sahip bir 'module' özniteliği olmalıdır

[Modülü](../../windows/module-cpp.md) özniteliği name parametresi olması gerekir.

Aşağıdaki örnek, C3131 oluşturur:

```
// C3131.cpp
[emitidl];
[module];   // C3131
// try the following line instead
// [module (name="MyLib")];

[public]
typedef long int LongInt;
```