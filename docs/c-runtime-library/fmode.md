---
title: _fmode | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- fmode
- _fmode
dev_langs:
- C++
helpviewer_keywords:
- file translation [C++], default mode
- fmode function
- _fmode function
ms.assetid: ac6df9eb-e5cc-4c54-aff3-373c21983118
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d4fdaeb0e67832f4f9e0c657e48fe74a88b86292
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="fmode"></a>_fmode
`_fmode` Değişkenini ayarlar metin veya ikili çeviri için varsayılan dosya çevirisi modu. Bu genel değişkeni daha güvenli işlevsel sürümleri için kullanım dışı [_get_fmode](../c-runtime-library/reference/get-fmode.md) ve [_set_fmode](../c-runtime-library/reference/set-fmode.md), hangi kullanılmalıdır yerine genel değişkeni. İçinde Stdlib.h gibi bildirilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
extern int _fmode;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Varsayılan ayar `_fmode` olan `_O_TEXT` metin modu çeviri için. `_O_BINARY`ikili mod ayardır.  
  
 Değerini değiştirebilir `_fmode` üç yolla:  
  
-   Binmode.obj içeren bağlantı. Bu ilk ayarını değiştirir `_fmode` için `_O_BINARY`, dışındaki tüm dosyaları neden `stdin`, `stdout`, ve `stderr` İkili modda açılacak.  
  
-   Çağırmaya `_get_fmode` veya `_set_fmode` almak veya ayarlamak için `_fmode` genel değişkeni sırasıyla.  
  
-   Değerini değiştirme `_fmode` programınıza ayarı tarafından doğrudan.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel değişkenler](../c-runtime-library/global-variables.md)   
 [_get_fmode](../c-runtime-library/reference/get-fmode.md)   
 [_set_fmode](../c-runtime-library/reference/set-fmode.md)