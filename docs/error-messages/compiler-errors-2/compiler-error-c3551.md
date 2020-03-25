---
title: Derleyici hatası C3551
ms.date: 11/04/2016
f1_keywords:
- C3551
helpviewer_keywords:
- C3551
ms.assetid: c8ee23da-6568-40db-93a6-3ddb7ac47712
ms.openlocfilehash: e9a4ce2276a602d59e495a2f336bb9d59dc0cc99
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80200765"
---
# <a name="compiler-error-c3551"></a>Derleyici hatası C3551

"geç belirtilen dönüş türü beklendi"

`auto` anahtar sözcüğünü bir işlevin dönüş türü için yer tutucu olarak kullanırsanız, bir geç belirtilen dönüş türü belirtmeniz gerekir. Aşağıdaki örnekte, `myFunction` işlevinin geç belirtilen dönüş türü, `int`türünde dört öğe dizisinin bir işaretçisidir.

```
auto myFunction()->int(*)[4];
```

## <a name="see-also"></a>Ayrıca bkz.

[auto](../../cpp/auto-cpp.md)
