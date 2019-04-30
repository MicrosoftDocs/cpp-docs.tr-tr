---
title: Derleyici Hatası C3551
ms.date: 11/04/2016
f1_keywords:
- C3551
helpviewer_keywords:
- C3551
ms.assetid: c8ee23da-6568-40db-93a6-3ddb7ac47712
ms.openlocfilehash: 48b378eb734c5830bedbf417d99d34955e2e6d0f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62375983"
---
# <a name="compiler-error-c3551"></a>Derleyici Hatası C3551

"bir sonradan belirtilen dönüş türü bekleniyordu"

Kullanırsanız `auto` anahtar sözcüğü bir işlevin dönüş türü için yer tutucu olarak sonradan belirtilmiş dönüş türü sağlamanız gerekir. Aşağıdaki örnekte, sonradan belirtilen dönüş türü işlev `myFunction` dört öğe türü bir dizi işaretçisidir `int`.

```
auto myFunction()->int(*)[4];
```

## <a name="see-also"></a>Ayrıca bkz.

[auto](../../cpp/auto-cpp.md)