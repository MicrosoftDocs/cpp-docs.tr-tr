---
title: _get_unexpected | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _get_unexpected
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- __get_unexpected
- _get_unexpected
- get_unexpected
dev_langs: C++
helpviewer_keywords:
- __get_unexpected function
- get_unexpected function
- _get_unexpected function
ms.assetid: a5f7a7a0-18e0-485e-953d-db291068a1e8
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 493dd3036e7f83ebf0e8fd94f62e57945ede52e4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="getunexpected"></a>_get_unexpected
Çağrılacak sonlandırma yordamı döndürür `unexpected`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
unexpected_function _get_unexpected( void );  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Tarafından kaydedilen işlevi için bir işaretçi döndüren [set_unexpected](../../c-runtime-library/reference/set-unexpected-crt.md). Hiçbir işlev ayarlarsanız dönüş değerini varsayılan davranışını geri yüklemek için kullanılabilir; Bu değer NULL olabilir.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_get_unexpected`|\<EH.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel durum işleme rutinleri](../../c-runtime-library/exception-handling-routines.md)   
 [durdurma](../../c-runtime-library/reference/abort.md)   
 [set_terminate](../../c-runtime-library/reference/set-terminate-crt.md)   
 [sonlandırma](../../c-runtime-library/reference/terminate-crt.md)   
 [beklenmeyen](../../c-runtime-library/reference/unexpected-crt.md)