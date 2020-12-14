---
description: 'Hakkında daha fazla bilgi edinin: &lt; codecvt &gt; enum'
title: '&lt;codecvt &gt; numaralandırmaları'
ms.date: 11/04/2016
f1_keywords:
- codecvt/std::codecvt_mode
ms.assetid: 46a8b073-01bc-46d3-b3d3-a8540f9422c1
helpviewer_keywords:
- std::codecvt_mode
ms.openlocfilehash: bcd40f72f563b3ecf91125f7167f206d4b1b6517
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234065"
---
# <a name="ltcodecvtgt-enums"></a>&lt;codecvt &gt; numaralandırmaları

## <a name="codecvt_mode-enumeration"></a><a name="codecvt_mode"></a> codecvt_mode numaralandırması

[Yerel ayar](../standard-library/locale-class.md) modelleri için yapılandırma bilgilerini belirtir.

```cpp
enum codecvt_mode {
    consume_header = 4,
    generate_header = 2,
    little_endian = 1
};
```

### <a name="remarks"></a>Açıklamalar

Sabit listesi, içinde belirtilen yerel ayar modellerine yapılandırma bilgilerini sağlayan üç sabiti tanımlar [\<codecvt>](../standard-library/codecvt.md) . DISTINCT değerleri şunlardır:

- `consume_header`, çok baytlı bir sırayı okurken bir başlangıç üst bilgi sırasını kullanmak ve daha sonra okunacak çok baytlı sıranın bitimliğini öğrenmek için

- `generate_header`bir çok baytlı sıra yazarken bir ilk üst bilgi sırası oluşturmak için, daha sonra yazılacak olan sonraki çok baytlı sıranın bitimliği

- `little_endian`, varsayılan Big-endian sırasından farklı olarak çok baytlı bir sıra oluşturmak için

Bu sabitler, rastgele birleşimlerde birlikte ORed olabilir.

## <a name="see-also"></a>Ayrıca bkz.

[\<codecvt>](../standard-library/codecvt.md)
