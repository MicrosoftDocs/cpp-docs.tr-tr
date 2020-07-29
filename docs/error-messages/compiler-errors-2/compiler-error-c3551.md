---
title: Derleyici hatası C3551
ms.date: 11/04/2016
f1_keywords:
- C3551
helpviewer_keywords:
- C3551
ms.assetid: c8ee23da-6568-40db-93a6-3ddb7ac47712
ms.openlocfilehash: 1555817de6e50ea27a021718c8b094efeaebacde
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230850"
---
# <a name="compiler-error-c3551"></a>Derleyici hatası C3551

"geç belirtilen dönüş türü beklendi"

**`auto`** Anahtar sözcüğünü bir işlevin dönüş türü için bir yer tutucu olarak kullanırsanız, bir geç belirtilen dönüş türü belirtmeniz gerekir. Aşağıdaki örnekte, işlevinin geç belirtilen dönüş türü, `myFunction` türünde dört öğe dizisinin bir işaretçisidir **`int`** .

```
auto myFunction()->int(*)[4];
```

## <a name="see-also"></a>Ayrıca bkz.

[auto](../../cpp/auto-cpp.md)
