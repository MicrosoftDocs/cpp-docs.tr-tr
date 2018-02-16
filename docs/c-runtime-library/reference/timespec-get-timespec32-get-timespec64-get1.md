---
title: timespec_get, _timespec32_get, _timespec64_get1 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- timespec_get
- _timespec32_get
- _timespec64_get
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
- timespec_get
- _timespec32_get
- _timespec64_get
- time/timespec_get
- time/_timespec32_get
- time/_timespec64_get
- timespec
- _timespec32
- _timespec64
dev_langs:
- C++
helpviewer_keywords:
- timespec_get function
- _timespec32_get function
- _timespec64_get function
ms.assetid: ed757258-b4f2-4c1d-a91b-22ea6ffce4ab
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 13b85eef72ed1a2180af1b41bf93eefe499967bd
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="timespecget-timespec32get-timespec64get"></a>timespec_get, _timespec32_get, _timespec64_get
Aralığı geçerli Takvim zaman için ilk bağımsız değişken gösterdiği kümeleri temel belirtilen süreye dayalı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int timespec_get(  
    struct timespec* const time_spec,  
    int const base  
);  
int _timespec32_get(  
    struct _timespec32* const time_spec,  
    int const base  
);  
int _timespec64_get(  
    struct _timespec64* const time_spec,  
    int const base  
);  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 `time_spec`  
 Dönem başladığından bu yana saniye ve nanosaniye zamana ayarlanan yapı işaretçi.  
  
 `base`  
 Süresi Temeli belirten sıfır uygulamaya özel değer.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Değeri `base` başarılı, aksi takdirde, sıfır durumunda döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 `timespec_get` İşlevleri gösterdiği yapısı geçerli saati kümesinde `time_spec` bağımsız değişkeni. Bu yapı'nin tüm sürümleri iki üyelere sahip `tv_sec` ve `tv_nsec`. `tv_sec` Değeri saniye tam sayıya ayarlanır ve `tv_nsec` nanosaniye tam sayı sayıya yuvarlanan sistem saati, çözümleme için tarafından belirtilen dönem başladığından bu yana `base`.  
  
 **Microsoft Specific**  
  
 Bu işlevler yalnızca Destek `TIME_UTC` olarak `base` değeri. Bu ayarlar `time_spec` değerine ve Dönem başlangıç olduğundan, gece yarısı, 1 Ocak 1970 Eşgüdümlü Evrensel Saat (UTC) nanosaniye saniye sayısı. İçinde bir `struct _timespec32`, `tv_sec` olan bir `__time32_t` değeri. İçinde bir `struct _timespec64`, `tv_sec` olan bir `__time64_t` değeri. İçinde bir `struct timespec`, `tv_sec` olan bir `time_t` 32 bit veya 64 bit uzunluğunda önişlemci makrosu _USE_32BIT_TIME_T olup tanımlanan bağlı olarak türü. `timespec_get` İşlevidir çağıran bir satır içi işlev `_timespec32_get` _USE_32BIT_TIME_T tanımlanmışsa; Aksi takdirde çağırır `_timespec64_get`.  
  
 **Son Microsoft özel**  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`timespec_get`, `_timespec32_get`, `_timespec64_get`|C: \<time.h >, C++: \<ctime > veya \<time.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Zaman Yönetimi](../../c-runtime-library/time-management.md)   
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [asctime_s, _wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [gmtime_s, _gmtime32_s, _gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [damgasını, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [_utime, _utime32, _utime64, _wutime, _wutime32, _wutime64](../../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md)