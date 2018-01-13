---
title: _get_tzname | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _get_tzname
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
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _get_tzname
- get_tzname
dev_langs: C++
helpviewer_keywords:
- _get_tzname function
- time zones
- get_tzname function
ms.assetid: df0065ff-095f-4237-832c-2fe9ab913875
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3f70e928c3877bf5d660231cbe2646f6cf72575e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="gettzname"></a>_get_tzname
Saat dilimi adı veya gün ışığından yararlanma standart saat dilimi adının (DST) karakteri dize gösterimini alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
errno_t _get_tzname(  
    size_t* pReturnValue,  
    char* timeZoneName,  
    size_t sizeInBytes,  
    int index      
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [out]`pReturnValue`  
 Dize uzunluğu `timeZoneName` NULL Sonlandırıcı dahil olmak üzere.  
  
 [out]`timeZoneName`  
 Bağlı olarak, saat dilimi adı veya gün ışığından yararlanma standart saat dilimi adının (DST) gösterimi için bir karakter dizesi adresini `index`.  
  
 [in]`sizeInBytes`  
 Boyutunu `timeZoneName` karakter bayt dizesi.  
  
 [in]`index`  
 Dizini almak için iki saat dilimi adlarından biri.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, sıfır Aksi halde bir `errno` değeri yazın.  
  
 Her iki `timeZoneName` olan `NULL`, veya `sizeInBytes` sıfır veya sıfır (ancak ikisi birden değil),'dan küçük bir geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Bu işlev devam etmek için yürütülmesine izin veriliyorsa, ayarlar `errno` için `EINVAL` ve döndürür `EINVAL`.  
  
### <a name="error-conditions"></a>Hata koşulları  
  
|`pReturnValue`|`timeZoneName`|`sizeInBytes`|`index`|Dönüş değeri|İçeriği`timeZoneName`|  
|--------------------|--------------------|-------------------|-------------|------------------|--------------------------------|  
|TZ adının boyutu|`NULL`|0|0 veya 1|0|değiştirilmedi|  
|TZ adının boyutu|tüm|> 0|0 veya 1|0|TZ adı|  
|değiştirilmedi|`NULL`|> 0|tüm|`EINVAL`|değiştirilmedi|  
|değiştirilmedi|tüm|sıfır|tüm|`EINVAL`|değiştirilmedi|  
|değiştirilmedi|tüm|> 0|> 1|`EINVAL`|değiştirilmedi|  
  
## <a name="remarks"></a>Açıklamalar  
 `_get_tzname` İşlevi alır karakteri dize gösterimini saat dilimi adı veya gün ışığından yararlanma standart saat dilimi adının (DST) adresini içine `timeZoneName` dizesinde boyutunu yanı sıra dizin değerine bağlı olarak `pReturnValue`. Varsa `timeZoneName` olan `NULL` ve `sizeInBytes` sıfır, yalnızca dize bayt bölgesinde döndürülür ya da zaman boyutu olduğu `pReturnValue`. Dizin değerleriyle standart saat dilimi için 0 veya 1 gün ışığından yararlanma standart saat dilimine yönelik olmalıdır; dizinin herhangi bir değere sahip belirlenmemiş sonuçları.  
  
### <a name="index-values"></a>Dizini değerleri  
  
|`index`|İçeriği`timeZoneName`|`timeZoneName`Varsayılan değer|  
|-------------|--------------------------------|----------------------------------|  
|0|Saat dilimi adı|"PASİFİK SAATİ"|  
|1.|Gün ışığından yararlanma standart saat dilimi adı|"SAATİ"|  
|1 > veya < 0|`errno`ayarlamak`EINVAL`|değiştirilmedi|  
  
 Değerleri açıkça çalışma zamanı sırasında değiştirilen sürece, varsayılan "PST" ve "Saati" sırasıyla değerlerdir.  Bu karakter dizileri boyutlarını tarafından yönetilir `TZNAME_MAX` değeri.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_get_tzname`|\<time.h >|  
  
 Daha fazla bilgi için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Zaman Yönetimi](../../c-runtime-library/time-management.md)   
 [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)   
 [_get_daylight](../../c-runtime-library/reference/get-daylight.md)   
 [_get_dstbias](../../c-runtime-library/reference/get-dstbias.md)   
 [_get_timezone](../../c-runtime-library/reference/get-timezone.md)   
 [TZNAME_MAX](../../c-runtime-library/tzname-max.md)