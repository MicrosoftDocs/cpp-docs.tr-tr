---
title: _strdate, _wstrdate | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _strdate
- _wstrdate
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
- _tstrdate
- wstrdate
- _wstrdate
- _strdate
- strdate
dev_langs:
- C++
helpviewer_keywords:
- strdate function
- dates, copying
- tstrdate function
- _wstrdate function
- wstrdate function
- _strdate function
- _tstrdate function
- copying dates
ms.assetid: de8e4097-58f8-42ba-9dcd-cb4d9a9f1696
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d81daed9666825446ab3a4a42ca0a9806531e2c2
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="strdate-wstrdate"></a>_strdate, _wstrdate
Geçerli sistem tarihi bir arabellek kopyalayın. Bu işlevlerin daha güvenli sürümleri kullanılabilir; bkz: [_strdate_s, _wstrdate_s](../../c-runtime-library/reference/strdate-s-wstrdate-s.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
char *_strdate(  
   char *datestr   
);  
wchar_t *_wstrdate(  
   wchar_t *datestr   
);  
template <size_t size>  
char *_strdate(  
   char (&datestr)[size]  
); // C++ only  
template <size_t size>  
wchar_t *_wstrdate(  
   wchar_t (&datestr)[size]  
); // C++ only  
```  
  
#### <a name="parameters"></a>Parametreler  
 `datestr`  
 Biçimlendirilmiş tarih dizesi içeren bir arabellek için bir işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bu işlevlerin her biri bir işaretçi sonuç karakter dizesi döndürür `datestr`.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlevlerin daha güvenli sürümleri kullanılabilir; bkz: [_strdate_s, _wstrdate_s](../../c-runtime-library/reference/strdate-s-wstrdate-s.md). Mümkün olduğunda daha güvenli işlevleri kullanılması önerilir.  
  
 `_strdate` İşlevi gösterdiği arabellek geçerli sistem tarihi kopyalar `datestr`biçimlendirilmiş `mm` / `dd` / `yy`, burada `mm` olan iki basamak temsil eden ay `dd` olan gününü temsil eden iki basamaklı ve `yy` yılın son iki basamaktan oluşur. Örneğin, dize `12/05/99` 5 Aralık 1999 temsil eder. Arabellek en az 9 bayt uzun olmalıdır.  
  
 Varsa `datestr` olan bir `NULL` işaretçi, geçersiz parametre işleyicisi çağrılır, açıklandığı gibi [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler -1 döndürür ve `errno` için `EINVAL`.  
  
 `_wstrdate` bir joker karakter sürümü `_strdate`; bağımsız değişkeni ve dönüş değeri `_wstrdate` joker karakter dizelerdir. Bu işlevler aynı şekilde aksi davranır.  
  
 C++'da, bu işlevlerin daha yeni, güvenli ortaklarınıza çağırma şablon aşırı yüklemeleri bu işlevler vardır. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tstrdate`|`_strdate`|`_strdate`|`_wstrdate`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_strdate`|\<time.h >|  
|`_wstrdate`|\<time.h > veya \<wchar.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
// strdate.c  
// compile with: /W3  
#include <time.h>  
#include <stdio.h>  
int main()  
{  
    char tmpbuf[9];  
  
    // Set time zone from TZ environment variable. If TZ is not set,  
    // the operating system is queried to obtain the default value   
    // for the variable.   
    //  
    _tzset();  
  
    printf( "OS date: %s\n", _strdate(tmpbuf) ); // C4996  
    // Note: _strdate is deprecated; consider using _strdate_s instead  
}  
```  
  
```Output  
OS date: 04/25/03  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Zaman Yönetimi](../../c-runtime-library/time-management.md)   
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [damgasını, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [mktime, _mktime32, _mktime64](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [_tzset](../../c-runtime-library/reference/tzset.md)