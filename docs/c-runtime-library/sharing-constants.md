---
title: "Paylaşım sabitleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _SH_DENYNO
- _SH_DENYRD
- _SH_DENYRW
- _SH_DENYWR
- _SH_COMPAT
dev_langs: C++
helpviewer_keywords:
- _SH_DENYRW constant
- SH_DENYRD constant
- _SH_COMPAT constant
- _SH_DENYRD constant
- SH_DENYRW constant
- sharing constants
- SH_DENYNO constant
- _SH_DENYWR constant
- SH_DENYWR constant
- _SH_DENYNO constant
- SH_COMPAT constant
ms.assetid: 95fadc3a-55dc-473d-98b5-e8211900465d
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 941cf63dd7a5eb761881e7068fa141d5e6b87a33
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="sharing-constants"></a>Paylaşım Sabitleri
Dosya Paylaşımı için sabitleri modları.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
#include <share.h>  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 *Shflag* bağımsız değişkeni bir veya daha fazla bildirim sabitleri oluşur Paylaşım modu belirler. Bunlar ile birleştirilebilir *oflag* bağımsız değişkenler (bkz [dosya sabitleri](../c-runtime-library/file-constants.md)).  
  
 Aşağıdaki tabloda, sabitleri ve anlamlarını listelenmektedir:  
  
|Sabit|Açıklama|  
|--------------|-------------|  
|`_SH_DENYRW`|Okuma ve yazma erişimi dosyaya engeller|  
|`_SH_DENYWR`|Dosyaya yazma erişimi engeller|  
|`_SH_DENYRD`|Dosyaya okuma erişimi engeller|  
|`_SH_DENYNO`|Okuma ve yazma erişimi verir|  
|`_SH_SECURE`|Ayarlar güvenli mod (paylaşılan okuma, özel yazma erişimi).|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md)   
 [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)   
 [Genel sabitler](../c-runtime-library/global-constants.md)