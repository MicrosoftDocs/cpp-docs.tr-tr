---
title: "Hata işleme (CRT) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.errors
dev_langs: C++
helpviewer_keywords:
- error handling, C routines for
- logic errors
- error handling, library routines
- testing, for program errors
ms.assetid: 125ac697-9eb0-4152-a440-b7842f23d97f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 176e744423441711715cc32b355278db20491e8f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="error-handling-crt"></a>Hata İşleme (CRT)
Program hataları işlemek için bu yordamları kullanın.  
  
### <a name="error-handling-routines"></a>Hata işleme rutinleri  
  
|Yordam|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|  
|-------------|---------|  
|[Assert](../c-runtime-library/reference/assert-macro-assert-wassert.md) makrosu|Mantık hataları programlama için test; Çalışma Zamanı Kitaplığı sürüm ve hata ayıklama sürümlerinde kullanılabilir.|  
|[_ASSERT, _ASSERTE](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) makroları|Benzer şekilde `assert`, ancak yalnızca çalışma zamanı kitaplığı hata ayıklama sürümlerinde kullanılabilir.|  
|[clearerr](../c-runtime-library/reference/clearerr.md)|Hata göstergesi sıfırlayın. Çağırma `rewind` veya bir akış kapatılırken de hata göstergesi sıfırlar.|  
|[_eof](../c-runtime-library/reference/eof.md)|Dosya düşük düzey g/ç sonunda olup olmadığını denetleyin.|  
|[feof](../c-runtime-library/reference/feof.md)|Dosya sonu için test edin. Dosya sonu olduğu da ne zaman gösterilen `_read` 0 döndürür.|  
|[ferror](../c-runtime-library/reference/ferror.md)|Akış g/ç hataları için test edin.|  
|[_RPT, _RPTF](../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md) makroları|Benzer şekilde bir raporu oluşturmak `printf`, ancak yalnızca çalışma zamanı kitaplığı hata ayıklama sürümlerinde kullanılabilir.|  
|[_set_error_mode](../c-runtime-library/reference/set-error-mode.md)|Değiştirir `__error_mode` C çalışma zamanı hata iletisi büyük olasılıkla program sona erer bir hata için nereye yazdığını varsayılan olmayan bir konum belirlemek için.|  
|[_set_purecall_handler](../c-runtime-library/reference/get-purecall-handler-set-purecall-handler.md)|Saf sanal işlev çağrısı için işleyici ayarlar.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kategorilere göre çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)