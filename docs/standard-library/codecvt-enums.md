---
title: '&lt;codecvt&gt; sabit listeleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- codecvt/std::codecvt_mode
ms.assetid: 46a8b073-01bc-46d3-b3d3-a8540f9422c1
helpviewer_keywords:
- std::codecvt_mode
ms.openlocfilehash: 612570680bfacb2bc9c237c60b3e9f6c4f8266a8
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45725341"
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
