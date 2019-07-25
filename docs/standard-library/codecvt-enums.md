---
title: '&lt;codecvt&gt; numaralandırmaları'
ms.date: 11/04/2016
f1_keywords:
- codecvt/std::codecvt_mode
ms.assetid: 46a8b073-01bc-46d3-b3d3-a8540f9422c1
helpviewer_keywords:
- std::codecvt_mode
ms.openlocfilehash: bbef1fe28c3321f06c0cc586062cd017168f8e73
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459788"
---
# <a name="ltcodecvtgt-enums"></a>&lt;codecvt&gt; numaralandırmaları

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

Sabit listesi, [ \<codecvt >](../standard-library/codecvt.md)içinde belirtilen yerel ayar modellerine yapılandırma bilgilerini sağlayan üç sabiti tanımlar. DISTINCT değerleri şunlardır:

- `consume_header`, çok baytlı bir sırayı okurken bir başlangıç üst bilgi sırasını kullanmak ve daha sonra okunacak çok baytlı sıranın bitimliğini öğrenmek için

- `generate_header`bir çok baytlı sıra yazarken bir ilk üst bilgi sırası oluşturmak için, daha sonra yazılacak olan sonraki çok baytlı sıranın bitimliği

- `little_endian`, varsayılan Big-endian sırasından farklı olarak çok baytlı bir sıra oluşturmak için

Bu sabitler, rastgele birleşimlerde birlikte ORed olabilir.

## <a name="see-also"></a>Ayrıca bkz.

[\<codecvt >](../standard-library/codecvt.md)
