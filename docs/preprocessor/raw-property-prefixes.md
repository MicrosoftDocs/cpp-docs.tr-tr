---
title: raw_property_prefixes
ms.date: 10/18/2018
f1_keywords:
- raw_property_prefixes
helpviewer_keywords:
- raw_property_prefixes attribute
ms.assetid: 03a0f48c-c460-4175-a762-9f7f8d84b12f
ms.openlocfilehash: 23250b524fdaa2181c8e28229ccec680ffdae715
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59033261"
---
# <a name="rawpropertyprefixes"></a>raw_property_prefixes

**C++ özgü**

Diğer özellik yöntemi için alternatif önekler belirtir.

## <a name="syntax"></a>Sözdizimi

```
raw_property_prefixes("GetPrefix","PutPrefix","PutRefPrefix")
```

### <a name="parameters"></a>Parametreler

*GetPrefix*<br/>
İçin kullanılacak önek `propget` yöntemleri.

*PutPrefix*<br/>
İçin kullanılacak önek `propput` yöntemleri.

*PutRefPrefix*<br/>
İçin kullanılacak önek `propputref` yöntemleri.

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, `propget`, `propput`, ve `propputref` yöntemleri önekleriyle adlandırılan üye işlevleri tarafından sunulur **get_**, **put_**, ve **propputref** sırasıyla. Bu önekler, MIDL tarafından oluşturulan üstbilgi dosyalarında kullanılan adlarla uyumludur.

**END C++ özgü**

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)