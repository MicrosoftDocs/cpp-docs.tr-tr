---
title: '&lt;codecvt&gt; numaralandırmalar'
ms.date: 11/04/2016
f1_keywords:
- codecvt/std::codecvt_mode
ms.assetid: 46a8b073-01bc-46d3-b3d3-a8540f9422c1
helpviewer_keywords:
- std::codecvt_mode
ms.openlocfilehash: bbef1fe28c3321f06c0cc586062cd017168f8e73
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78866164"
---
# <a name="ltcodecvtgt-enums"></a>&lt;codecvt&gt; numaralandırmalar

## <a name="codecvt_mode"></a>codecvt_mode numaralandırması

[Yerel ayar](../standard-library/locale-class.md) modelleri için yapılandırma bilgilerini belirtir.

```cpp
enum codecvt_mode {
    consume_header = 4,
    generate_header = 2,
    little_endian = 1
};
```

### <a name="remarks"></a>Açıklamalar

Sabit listesi, [\<codecvt >](../standard-library/codecvt.md)tarafından belirtilen yerel ayar modellerine yapılandırma bilgilerini sağlayan üç sabiti tanımlar. DISTINCT değerleri şunlardır:

- `consume_header`, çok baytlı bir sırayı okurken ilk üst bilgi sırasını tüketmek ve sonraki çok baytlı sıranın okunması için bitimliği belirleme

- `generate_header`, sonraki çok baytlı sıranın yazılması için çok baytlı bir sıra yazarken ilk başlık sırası oluşturmak için

- `little_endian`, varsayılan Big-endian sırasından farklı olarak çok baytlı bir sıra oluşturmak için

Bu sabitler, rastgele birleşimlerde birlikte ORed olabilir.

## <a name="see-also"></a>Ayrıca bkz.

[\<codecvt >](../standard-library/codecvt.md)
