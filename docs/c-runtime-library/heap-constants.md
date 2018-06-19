---
title: Yığın sabitleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- _HEAPBADPTR
- _HEAPEMPTY
- _HEAPBADBEGIN
- _HEAPOK
- _HEAPBADNODE
- _HEAPEND
dev_langs:
- C++
helpviewer_keywords:
- _HEAPOK constants
- _HEAPEND constants
- HEAPBADBEGIN constants
- _HEAPBADNODE constants
- HEAPBADNODE constants
- HEAPBADPTR constants
- _HEAPEMPTY constants
- HEAPEND constants
- HEAPOK constants
- HEAPEMPTY constants
- _HEAPBADBEGIN constants
- _HEAPBADPTR constants
- heap constants
ms.assetid: 3f751bb9-2dc4-486f-b5f5-9061c96d3754
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 25118792500d679d243f55e5d87e62a4994eaa0f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32389936"
---
# <a name="heap-constants"></a>Yığın Sabitleri
## <a name="syntax"></a>Sözdizimi  
  
```  
  
#include <malloc.h>  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sabitleri öbek durumunu gösteren dönüş değeri verin.  
  
|Sabit|Açıklama|  
|--------------|-------------|  
|`_HEAPBADBEGIN`|İlk üst bilgileri bulunamadı veya geçersizdi.|  
|`_HEAPBADNODE`|Yığın zarar görmüş veya hatalı düğüm bulunamadı.|  
|`_HEAPBADPTR`|**_pentry** alanını **_heapınfo** yapısı geçerli işaretçi yığına içermiyor (`_heapwalk` yordamı yalnızca).|  
|`_HEAPEMPTY`|Yığın başlatılmadı.|  
|`_HEAPEND`|Yığın sonuna başarıyla ulaşıldı (`_heapwalk` yordamı yalnızca).|  
|`_HEAPOK`|Yığın tutarlıdır (`_heapset` ve `_heapchk` yalnızca yordamları). Hiçbir hata kadarki; **_Heapınfo** yapısı sonraki giriş hakkında bilgiler içerir (`_heapwalk` yordamı yalnızca).|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_heapchk](../c-runtime-library/reference/heapchk.md)   
 [_heapset](../c-runtime-library/heapset.md)   
 [_heapwalk](../c-runtime-library/reference/heapwalk.md)   
 [Global Sabitler](../c-runtime-library/global-constants.md)