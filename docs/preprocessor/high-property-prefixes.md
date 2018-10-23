---
title: high_property_prefixes | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- high_property_prefixes
dev_langs:
- C++
helpviewer_keywords:
- high_property_prefixes attribute
ms.assetid: 91c6cc2b-19b6-4aba-8831-d9e5cccb58b5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e3932a7632b12120e722c5f375f4387e08f1853b
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49809063"
---
# <a name="highpropertyprefixes"></a>high_property_prefixes

**C++ özgü**

Diğer özellik yöntemi için alternatif önekler belirtir.

## <a name="syntax"></a>Sözdizimi

```
high_property_prefixes("GetPrefix","PutPrefix","PutRefPrefix")
```

### <a name="parameters"></a>Parametreler

*GetPrefix*<br/>
İçin kullanılacak önek `propget` yöntemleri.

*PutPrefix*<br/>
İçin kullanılacak önek `propput` yöntemleri.

*PutRefPrefix*<br/>
İçin kullanılacak önek `propputref` yöntemleri.

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, üst düzey hata işleme `propget`, `propput`, ve `propputref` yöntemleri önekleriyle adlandırılan üye işlevleri tarafından sunulur `Get`, `Put`, ve `PutRef`sırasıyla.

**END C++ özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)