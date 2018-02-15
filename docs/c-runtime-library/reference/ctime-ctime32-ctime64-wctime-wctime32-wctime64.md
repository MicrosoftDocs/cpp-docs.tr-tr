---
title: ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _ctime64
- _wctime32
- ctime
- _wctime64
- _ctime32
- _wctime
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
- _wctime64
- _ctime32
- _tctime
- _wctime
- _wctime32
- _tctime64
- _ctime64
- ctime
dev_langs:
- C++
helpviewer_keywords:
- tctime64 function
- _ctime32 function
- ctime32 function
- _wctime function
- wctime64 function
- _tctime64 function
- _tctime32 function
- _ctime64 function
- _wctime64 function
- ctime function
- wctime32 function
- ctime64 function
- _wctime32 function
- _tctime function
- tctime32 function
- tctime function
- wctime function
- time, converting
ms.assetid: 2423de37-a35c-4f0a-a378-3116bc120a9d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c3154b71654f0b4fc944daa94a354db32c981c2f
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="ctime-ctime32-ctime64-wctime-wctime32-wctime64"></a>ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64
Bir saat değeri dizeye ve yerel saat dilimi ayarlarını yapın. Bu işlevlerin daha güvenli sürümleri kullanılabilir; bkz: [ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
char *ctime(   
   const time_t *timer   
);  
char *_ctime32(   
   const __time32_t *timer )  
;  
char *_ctime64(   
   const __time64_t *timer )  
;  
wchar_t *_wctime(   
   const time_t *timer   
);  
wchar_t *_wctime32(   
   const __time32_t *timer  
);  
wchar_t *_wctime64(   
   const __time64_t *timer   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `timer`  
 Saklı zaman işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Karakter dizesi sonucu için bir işaretçi. `NULL` olursa döndürülür:  
  
-   `time` gece yarısından, 1 Ocak 1970 UTC tarihi temsil eder.  
  
-   Kullanırsanız `_ctime32` veya `_wctime32` ve `time` 23:59:59 18 Ocak 2038, UTC tarihinden temsil eder.  
  
-   Kullanırsanız `_ctime64` veya `_wctime64` ve `time` 23:59:59 31 Aralık 3000 UTC tarihinden temsil eder.  
  
 `ctime` için değerlendiren bir satır içi işlev `_ctime64` ve `time_t` eşdeğerdir `__time64_t`. Yorumlamaya derleyici zorlamak gerekiyorsa `time_t` eski 32 bit olarak `time_t`, tanımlayabileceğiniz `_USE_32BIT_TIME_T`. Bunun neden olacak `ctime` için değerlendirilecek `_ctime32`. Bu, uygulamanızın 18 Ocak 2038 sonra başarısız olabilir ve 64 bit platformlarda izin verilmiyor çünkü önerilmez.  
  
## <a name="remarks"></a>Açıklamalar  
 `ctime` İşlevi dönüştürür olarak saklanan bir saat değeri bir [time_t](../../c-runtime-library/standard-types.md) bir karakter dizesine değeri. `timer` Değeri çağrısından alınan genellikle [zaman](../../c-runtime-library/reference/time-time32-time64.md), gece yarısından beri geçen saniye sayısı döndüren (00: 00:00), 1 Ocak 1970'den itibaren Eşgüdümlü Evrensel Saat (UTC). Dönüş değeri dize tam olarak 26 karakter içerir ve biçime sahiptir:  
  
```  
Wed Jan 02 02:03:55 1980\n\0  
```  
  
 24 saatlik kullanılır. Tüm alanları sabit genişlik sahiptir. Yeni satır karakteri ('\n') ve null karakteri ('\0') dize son iki konumlarını kaplar.  
  
 Dönüştürülen karakter dizesini de yerel saat dilimi ayarlarını göre ayarlanır. Bkz `time`, [_ftime](../../c-runtime-library/reference/ftime-ftime32-ftime64.md), ve [damgasını](../../c-runtime-library/reference/localtime-localtime32-localtime64.md) yerel saat yapılandırma hakkında bilgi için İşlevler ve [_tzset](../../c-runtime-library/reference/tzset.md) tanımlama hakkında ayrıntılar için işlevi saat dilimi ortam ve genel değişkenler.  
  
 Çağrı `ctime` tarafından kullanılan tek bir statik olarak ayrılan arabelleğe değiştirir `gmtime` ve `localtime` işlevleri. Bu yordamlar her çağrısına önceki çağrının sonucu bozar. `ctime` statik bir arabellekle paylaşır `asctime` işlevi. Bu nedenle, yapılan bir çağrı `ctime` önceki tüm arama sonuçlarını bozar `asctime`, `localtime`, veya `gmtime`.  
  
 `_wctime` ve `_wctime64` joker karakter sürümüne sahip `ctime` ve `_ctime64`; joker karakter dizesi için bir işaretçi döndürüyor. Aksi takdirde, `_ctime64`, `_wctime`, ve `_wctime64` aynı şekilde davranır `ctime`.  
  
 Bu işlevler kendi parametreleri doğrulayın. Varsa `timer` null işaretçi ya da devre dışı zamanlayıcı değeri negatifse, bu işlevler geçersiz parametre işleyicisi açıklandığı gibi çağırma [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Yürütme devam etmek için izin verilip verilmediğini, işlevlerin dönüş `NULL` ve `errno` için `EINVAL`.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tctime`|`ctime`|`ctime`|`_wctime`|  
|`_tctime32`|`_ctime32`|`_ctime32`|`_wctime32`|  
|`_tctime64`|`_ctime64`|`_ctime64`|`_wctime64`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`ctime`|\<time.h >|  
|`_ctime32`|\<time.h >|  
|`_ctime64`|\<time.h >|  
|`_wctime`|\<time.h > veya \<wchar.h >|  
|`_wctime32`|\<time.h > veya \<wchar.h >|  
|`_wctime64`|\<time.h > veya \<wchar.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_ctime64.c  
// compile with: /W3  
/* This program gets the current  
 * time in _time64_t form, then uses ctime to  
 * display the time in string form.  
 */  
  
#include <time.h>  
#include <stdio.h>  
  
int main( void )  
{  
   __time64_t ltime;  
  
   _time64( &ltime );  
   printf( "The time is %s\n", _ctime64( &ltime ) ); // C4996  
   // Note: _ctime64 is deprecated; consider using _ctime64_s  
}  
```  
  
```Output  
The time is Wed Feb 13 16:04:43 2002  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Zaman Yönetimi](../../c-runtime-library/time-management.md)   
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [damgasını, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)