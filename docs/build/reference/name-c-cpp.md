---
description: 'Daha fazla bilgi edinin: adı (C/C++)'
title: NAME (C/C++)
ms.date: 11/04/2016
f1_keywords:
- name
helpviewer_keywords:
- NAME .def file statement
ms.assetid: 5c9b6bd8-9275-46a5-afba-f17a5936dc26
ms.openlocfilehash: 7444aa20539b47b1f04d17a266a0b65a552af3f3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97137780"
---
# <a name="name-cc"></a>NAME (C/C++)

Ana çıkış dosyası için bir ad belirtir.

```
NAME [application][BASE=address]
```

## <a name="remarks"></a>Açıklamalar

Bir çıkış dosyası adını belirtmenin eşdeğer bir yolu, [/Out](out-output-file-name.md) bağlayıcı seçeneğiyle birlikte temel adresi ayarlamak için de eşdeğer bir yoldur ve [/Base](base-base-address.md) bağlayıcı seçeneğidir. Her ikisi de belirtilirse,/OUT geçersiz kılmalar **adı**.

DLL oluşturursanız, ad yalnızca DLL adını etkiler.

## <a name="see-also"></a>Ayrıca bkz.

[Module-Definition deyimleri için kurallar](rules-for-module-definition-statements.md)
