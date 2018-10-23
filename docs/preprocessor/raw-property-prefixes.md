---
title: raw_property_prefixes | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- raw_property_prefixes
dev_langs:
- C++
helpviewer_keywords:
- raw_property_prefixes attribute
ms.assetid: 03a0f48c-c460-4175-a762-9f7f8d84b12f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1170440428a5c92e383152826827989d602e69fb
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49808751"
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

## <a name="see-also"></a>Ayrıca Bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)