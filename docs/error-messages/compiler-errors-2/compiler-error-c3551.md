---
title: Derleyici Hatası C3551 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3551
dev_langs:
- C++
helpviewer_keywords:
- C3551
ms.assetid: c8ee23da-6568-40db-93a6-3ddb7ac47712
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b45a6f66ab7cf2a5ebb7ae6b2a2f78e664092604
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035740"
---
# <a name="compiler-error-c3551"></a>Derleyici Hatası C3551

"bir sonradan belirtilen dönüş türü bekleniyordu"

Kullanırsanız `auto` anahtar sözcüğü bir işlevin dönüş türü için yer tutucu olarak sonradan belirtilmiş dönüş türü sağlamanız gerekir. Aşağıdaki örnekte, sonradan belirtilen dönüş türü işlev `myFunction` dört öğe türü bir dizi işaretçisidir `int`.

```
auto myFunction()->int(*)[4];
```

## <a name="see-also"></a>Ayrıca Bkz.

[auto](../../cpp/auto-cpp.md)