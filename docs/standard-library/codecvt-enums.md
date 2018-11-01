---
title: '&lt;codecvt&gt; sabit listeleri'
ms.date: 11/04/2016
f1_keywords:
- codecvt/std::codecvt_mode
ms.assetid: 46a8b073-01bc-46d3-b3d3-a8540f9422c1
helpviewer_keywords:
- std::codecvt_mode
ms.openlocfilehash: 0b43c7c148076e96dd0d3f444ffa8b6bad7c8b29
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50566162"
---
# <a name="ltcodecvtgt-enums"></a>&lt;codecvt&gt; sabit listeleri

## <a name="codecvt_mode"></a>  codecvt_mode numaralandırması

Yapılandırma bilgilerini belirtir [yerel ayar](../standard-library/locale-class.md) modeller.

```cpp
enum codecvt_mode {
    consume_header = 4,
    generate_header = 2,
    little_endian = 1
};
```

### <a name="remarks"></a>Açıklamalar

Bildirilen yerel ayar modelleri için yapılandırma bilgilerini sağlayın, üç sabitleri sabit listesi tanımlar [ \<codecvt >](../standard-library/codecvt.md). Farklı değerler şunlardır:

- `consume_header`, çok baytlı bir sıra okunurken ilk üstbilgi dizisi kullanmak ve okumak için sonraki çok baytlı dizisi endianness belirlemek için

- `generate_header`, yazılacak sonraki çok baytlı dizisi endianness bildirmek üzere bir çok baytlı dizisi yazarken ilk üstbilgi dizisi oluşturmak için

- `little_endian`, varsayılan büyük endian sırası aksine endian sırasıyla bir çok baytlı dizisi oluşturmak için

Bu sabitlerden ORed birlikte rastgele kombinasyonları için geçerli olabilir.

## <a name="see-also"></a>Ayrıca bkz.

[\<codecvt >](../standard-library/codecvt.md)<br/>
