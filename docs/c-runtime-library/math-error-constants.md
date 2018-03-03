---
title: "Matematik hatası sabitleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _PLOSS
- _UNDERFLOW
- _TLOSS
- _SING
- _DOMAIN
- _OVERFLOW
dev_langs:
- C++
helpviewer_keywords:
- _TLOSS constant
- _SING constant
- PLOSS constant
- UNDERFLOW constant
- _UNDERFLOW constant
- _OVERFLOW constant
- DOMAIN constant
- OVERFLOW constant
- TLOSS constant
- SING constant
- _DOMAIN constant
- _PLOSS constant
- math error constants
ms.assetid: 4be933a6-674e-45a5-8ac9-090023542f5b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 76313854bc9bb7c9a624836c47d0178978f8befd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="math-error-constants"></a>Matematik Hatası Sabitleri
## <a name="syntax"></a>Sözdizimi  
  
```  
  
#include <math.h>  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Matematik yordamları çalışma zamanı kitaplığı matematik hatası sabitleri oluşturabilir.  
  
 Açıklandığı gibi bu hataları MATEMATİK içinde tanımlanmış özel durum türleri karşılık gelir. H ve bu tarafından döndürülen `_matherr` bir matematik hatası oluştuğunda işlev.  
  
|Sabit|Açıklama|  
|--------------|-------------|  
|`_DOMAIN`|İşlev bağımsız değişkeni dışında işlevinin etki alanıdır.|  
|`_OVERFLOW`|Sonuç, işlevin dönüş türünü gösterilemeyecek kadar çok büyük.|  
|`_PLOSS`|Kısmi bir kayıp anlamlı oluştu.|  
|`_SING`|Bağımsız değişken singularity: işlevine bağımsız değişken geçersiz değere sahip. (Örneğin, 0 değeri, sıfır olmayan bir değer gerektiren işlevi geçirilir.)|  
|`_TLOSS`|Anlamlı toplam kaybı oluştu.|  
|`_UNDERFLOW`|Sonuç gösterilemeyecek kadar çok küçük.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_matherr](../c-runtime-library/reference/matherr.md)   
 [Global Sabitler](../c-runtime-library/global-constants.md)