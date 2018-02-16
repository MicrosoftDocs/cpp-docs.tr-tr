---
title: _get_dstbias | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _get_dstbias
- __dstbias
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
- __dstbias
- _get_dstbias
- get_dstbias
dev_langs:
- C++
helpviewer_keywords:
- __dstbias
- daylight saving time offset
- get_dstbias function
- _get_dstbias function
ms.assetid: e751358c-1ecc-411b-ae2c-81b2ec54ea45
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4f6d43b904b96f7323c76637d1f38c024d4696f1
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="getdstbias"></a>_get_dstbias
Yaz Saati farkı saniye cinsinden alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      error_t _get_dstbias(   
    int* seconds  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `seconds`  
 Yaz Saati saniye cinsinden uzaklık.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa ya da bir sıfır `errno` bir hata oluşursa değeri.  
  
## <a name="remarks"></a>Açıklamalar  
 `_get_dstbias` İşlevi bir tamsayı olarak gün ışığından yararlanma saati saniye sayısını alır. Yaz Saati etkinse, varsayılan 3600 saniye (birkaç bölgeler iki saatlik uzaklığı gözlemlemek rağmen) bir saat içinde saniye sayısını olduğu uzaklığı.  
  
 Varsa `seconds` olan `NULL`, geçersiz parametre işleyicisi açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Bu işlev devam etmek için yürütülmesine izin veriliyorsa, ayarlar `errno` için `EINVAL` ve döndürür `EINVAL`.  
  
 Makro yerine bu işlev kullanmanızı öneririz `_dstbias` veya kullanım dışı işlev `__dstbias`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_get_dstbias`|\<time.h >|  
  
 Daha fazla bilgi için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Zaman Yönetimi](../../c-runtime-library/time-management.md)   
 [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)   
 [_get_daylight](../../c-runtime-library/reference/get-daylight.md)   
 [_get_timezone](../../c-runtime-library/reference/get-timezone.md)   
 [_get_tzname](../../c-runtime-library/reference/get-tzname.md)