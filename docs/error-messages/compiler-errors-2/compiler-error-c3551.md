---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3551'
title: Derleyici hatası C3551
ms.date: 11/04/2016
f1_keywords:
- C3551
helpviewer_keywords:
- C3551
ms.assetid: c8ee23da-6568-40db-93a6-3ddb7ac47712
ms.openlocfilehash: 813d483b696d0829f05108a35e5731f93f6004ea
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223275"
---
# <a name="compiler-error-c3551"></a>Derleyici hatası C3551

"geç belirtilen dönüş türü beklendi"

**`auto`** Anahtar sözcüğünü bir işlevin dönüş türü için bir yer tutucu olarak kullanırsanız, bir geç belirtilen dönüş türü belirtmeniz gerekir. Aşağıdaki örnekte, işlevinin geç belirtilen dönüş türü, `myFunction` türünde dört öğe dizisinin bir işaretçisidir **`int`** .

```
auto myFunction()->int(*)[4];
```

## <a name="see-also"></a>Ayrıca bkz.

[Otomatik](../../cpp/auto-cpp.md)
