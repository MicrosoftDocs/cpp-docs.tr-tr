---
title: '&lt;codecvt&gt; enums'
ms.date: 11/04/2016
f1_keywords:
- codecvt/std::codecvt_mode
ms.assetid: 46a8b073-01bc-46d3-b3d3-a8540f9422c1
helpviewer_keywords:
- std::codecvt_mode
ms.openlocfilehash: e67290d8de0b8251191c4a93b66b7e19a293ed61
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371939"
---
# <a name="ltcodecvtgt-enums"></a>&lt;codecvt&gt; enums

## <a name="codecvt_mode-enumeration"></a><a name="codecvt_mode"></a>codecvt_mode Numaralandırma

[Yerel](../standard-library/locale-class.md) yüzler için yapılandırma bilgilerini belirtir.

```cpp
enum codecvt_mode {
    consume_header = 4,
    generate_header = 2,
    little_endian = 1
};
```

### <a name="remarks"></a>Açıklamalar

Numaralandırma, [ \<codecvt>'da ](../standard-library/codecvt.md)bildirilen yerel yüzlere yapılandırma bilgileri sağlayan üç sabit tanımlar. Farklı değerler şunlardır:

- `consume_header`, çok baytlı bir dizi okurken bir başlangıç üstbilgi dizisi tüketmek ve okunacak sonraki çok bayt dizisinin sonnoktalarını belirlemek

- `generate_header`, yazılması gereken sonraki çok bayt dizisinin sonluluğunu bildirmek için çok baytlık bir dizi yazarken bir başlangıç üstbilgi dizisi oluşturmak için

- `little_endian`, varsayılan büyük endian sırasıyerine, küçük endian sırayla bir çok bayt dizisi oluşturmak için

Bu sabitler rasgele kombinasyonlarda birlikte ored olabilir.

## <a name="see-also"></a>Ayrıca bkz.

[\<codecvt>](../standard-library/codecvt.md)
