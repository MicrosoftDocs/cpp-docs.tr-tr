---
title: NAME (C/C++)
ms.date: 11/04/2016
f1_keywords:
- name
helpviewer_keywords:
- NAME .def file statement
ms.assetid: 5c9b6bd8-9275-46a5-afba-f17a5936dc26
ms.openlocfilehash: c05e82409d6b6e48390d54160e8ff23ada788d41
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50646205"
---
# <a name="name-cc"></a>NAME (C/C++)

Ana çıkış dosyası adını belirtir.

```
NAME [application][BASE=address]
```

## <a name="remarks"></a>Açıklamalar

Çıkış dosyası adı belirtmek için eşdeğer bir yöntem, [/OUT](../../build/reference/out-output-file-name.md) bağlayıcı seçeneği ve temel adresi ayarlamak için eşdeğer bir yolu olan [/BASE](../../build/reference/base-base-address.md) bağlayıcı seçeneği. Her ikisi de belirtilirse, / OUT geçersiz kılar, **adı**.

Bir DLL yapılandırdıysanız, adı yalnızca DLL adı etkiler.

## <a name="see-also"></a>Ayrıca Bkz.

[Modül Tanımlama Deyimleri Kuralları](../../build/reference/rules-for-module-definition-statements.md)