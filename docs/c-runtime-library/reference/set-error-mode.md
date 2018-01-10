---
title: _set_error_mode | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _set_error_mode
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- set_error_mode
- _set_error_mode
dev_langs: C++
helpviewer_keywords:
- _set_error_mode function
- set_error_mode function
ms.assetid: f0807be5-73d1-4a32-a701-3c9bdd139c5c
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7987686fb0b9faa03cf4d5e4795116e9f0a608bd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="seterrormode"></a>_set_error_mode
Değiştirir `__error_mode` C çalışma zamanı hata iletisi programın sonlandırılması bir hata için nereye yazdığını varsayılan olmayan konumunu belirlemek için.  
  
> [!IMPORTANT]
>  Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [/ZW ile desteklenmeyen CRT işlevleri](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _set_error_mode(  
   int modeval   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `modeval`  
 Hata iletileri hedef.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir hata oluşursa eski ayarı veya -1 döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Hata çıkış havuzunun değerini ayarlayarak denetimleri `__error_mode`. Örneğin, doğrudan bir standart hata çıktısı veya kullanmak `MessageBox` API.  
  
 `modeval` Parametresi şu değerlerden biri olarak ayarlanabilir.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`_OUT_TO_DEFAULT`|Hata havuz tarafından belirlenir `__app_type`.|  
|`_OUT_TO_STDERR`|Hata havuz standart bir hatadır.|  
|`_OUT_TO_MSGBOX`|Hata havuz bir ileti kutusu ' dir.|  
|`_REPORT_ERRMODE`|Geçerli rapor `__error_mode` değeri.|  
  
 Bu listedeki dışında bir değer geçtiyse, geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa `_set_error_mode` ayarlar `errno` için `EINVAL` ve -1 döndürür.  
  
 İle kullanıldığında bir [assert](../../c-runtime-library/reference/assert-macro-assert-wassert.md), `_set_error_mode` seçme seçeneği sunar ve iletişim kutusunda başarısız deyimi görüntüler `Ignore` programı çalıştırmak devam edebilmesi için bu düğme.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_set_error_mode`|\<stdlib.h >|  
  
## <a name="example"></a>Örnek  
  
```C  
// crt_set_error_mode.c  
// compile with: /c  
#include <stdlib.h>  
#include <assert.h>  
  
int main()  
{  
   _set_error_mode(_OUT_TO_STDERR);  
   assert(2+2==5);  
}  
```  
  
```Output  
Assertion failed: 2+2==5, file crt_set_error_mode.c, line 8  
  
This application has requested the Runtime to terminate it in an unusual way.  
Please contact the application's support team for more information.  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [assert Makrosu, _assert, _wassert](../../c-runtime-library/reference/assert-macro-assert-wassert.md)