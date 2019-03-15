---
title: NAME (C/C++)
ms.date: 11/04/2016
f1_keywords:
- name
helpviewer_keywords:
- NAME .def file statement
ms.assetid: 5c9b6bd8-9275-46a5-afba-f17a5936dc26
ms.openlocfilehash: d0813befc622db72e095c449794405fc5d58465b
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57812193"
---
# <a name="name-cc"></a>NAME (C/C++)

Ana çıkış dosyası adını belirtir.

```
NAME [application][BASE=address]
```

## <a name="remarks"></a>Açıklamalar

Çıkış dosyası adı belirtmek için eşdeğer bir yöntem, [/OUT](out-output-file-name.md) bağlayıcı seçeneği ve temel adresi ayarlamak için eşdeğer bir yolu olan [/BASE](base-base-address.md) bağlayıcı seçeneği. Her ikisi de belirtilirse, / OUT geçersiz kılar, **adı**.

Bir DLL yapılandırdıysanız, adı yalnızca DLL adı etkiler.

## <a name="see-also"></a>Ayrıca bkz.

[Modül Tanımlama Deyimleri Kuralları](rules-for-module-definition-statements.md)
