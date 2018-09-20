---
title: raw_property_prefixes | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 3ae69e26077692188b8e013e949592df26d7701a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46420406"
---
# <a name="rawpropertyprefixes"></a>raw_property_prefixes
**C++ özgü**  
  
Diğer özellik yöntemi için alternatif önekler belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
raw_property_prefixes("GetPrefix","PutPrefix","PutRefPrefix")  
```  
  
### <a name="parameters"></a>Parametreler  
*GetPrefix*  
İçin kullanılacak önek `propget` yöntemleri.  
  
*PutPrefix*  
İçin kullanılacak önek `propput` yöntemleri.  
  
*PutRefPrefix*  
İçin kullanılacak önek `propputref` yöntemleri.  
  
## <a name="remarks"></a>Açıklamalar  
 
Varsayılan olarak, `propget`, `propput`, ve `propputref` yöntemleri önekleriyle adlandırılan üye işlevleri tarafından sunulur **get_**, **put_**, ve **propputref** sırasıyla. Bu önekler, MIDL tarafından oluşturulan üstbilgi dosyalarında kullanılan adlarla uyumludur.  
  
**END C++ özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 
[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)