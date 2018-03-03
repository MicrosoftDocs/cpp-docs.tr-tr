---
title: "Paylaşım sabitleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _SH_DENYNO
- _SH_DENYRD
- _SH_DENYRW
- _SH_DENYWR
- _SH_COMPAT
dev_langs:
- C++
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 635c6eee50f5d1dfb19f0c1b823dab018922c490
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [Global Sabitler](../c-runtime-library/global-constants.md)