---
title: Derleyici Hatası C3551
ms.date: 11/04/2016
f1_keywords:
- C3551
helpviewer_keywords:
- C3551
ms.assetid: c8ee23da-6568-40db-93a6-3ddb7ac47712
ms.openlocfilehash: 9dfdee155e85bd772ed1d4ce22c525f8a4c79f5c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50458753"
---
# <a name="compiler-error-c3551"></a>Derleyici Hatası C3551

"bir sonradan belirtilen dönüş türü bekleniyordu"

Kullanırsanız `auto` anahtar sözcüğü bir işlevin dönüş türü için yer tutucu olarak sonradan belirtilmiş dönüş türü sağlamanız gerekir. Aşağıdaki örnekte, sonradan belirtilen dönüş türü işlev `myFunction` dört öğe türü bir dizi işaretçisidir `int`.

```
auto myFunction()->int(*)[4];
```

## <a name="see-also"></a>Ayrıca Bkz.

[auto](../../cpp/auto-cpp.md)