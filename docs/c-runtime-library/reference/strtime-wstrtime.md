---
title: _strtime, _wstrtime | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wstrtime
- _strtime
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
- _wstrtime
- _strtime
- wstrtime
- strtime
- _tstrtime
dev_langs:
- C++
helpviewer_keywords:
- strtime function
- _strtime function
- _wstrtime function
- copying time to buffers
- wstrtime function
- tstrtime function
- _tstrtime function
- time, copying
ms.assetid: 9e538161-cf49-44ec-bca5-c0ab0b9e4ca3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b2881cc0b026225674096127eba165b622483de3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="strtime-wstrtime"></a>_strtime, _wstrtime

Zaman bir arabellek kopyalayın. Bu işlevlerin daha güvenli sürümleri kullanılabilir; bkz: [_strtime_s, _wstrtime_s](strtime-s-wstrtime-s.md).

## <a name="syntax"></a>Sözdizimi

```C
char *_strtime(
   char *timestr
);
wchar_t *_wstrtime(
   wchar_t *timestr
);
template <size_t size>
char *_strtime(
   char (&timestr)[size]
); // C++ only
template <size_t size>
wchar_t *_wstrtime(
   wchar_t (&timestr)[size]
); // C++ only
```

### <a name="parameters"></a>Parametreler

*timestr*<br/>
Saat dizesi.

## <a name="return-value"></a>Dönüş Değeri

Bir işaretçi sonuç karakter dizesi döndürür *timestr*.

## <a name="remarks"></a>Açıklamalar

**_Strtime** işlevi geçerli yerel saat gösterdiği arabellek kopyalar *timestr*. Saat olarak biçimlendirilmiş **ss: dd:** nerede **hh** olan 24 saatlik gösteriminde saati temsil eden iki basamak **mm** olan saat ve geçetemsiledenikibasamak**ss** saniye temsil eden iki basamak değil. Örneğin, dize **18:23:44** 23 dakika ve 44 aşan saniye 6'da temsil eder Arabellek en az 9 bayt uzun olmalıdır.

**_wstrtime** bir joker karakter sürümü **_strtime**; bağımsız değişkeni ve dönüş değeri **_wstrtime** joker karakter dizelerdir. Bu işlevler aynı şekilde aksi davranır. Varsa *timestr* olan **NULL** işaretçi veya *timestr* geçersiz yanlış biçimlendirilmiş parametre işleyicisi çağrılır, açıklandığı gibi [parametresi Doğrulama](../../c-runtime-library/parameter-validation.md). Özel durum, devam etmek için bu işlevler dönüş NULL ve kümesi izin verilip verilmediğini **errno** için **EINVAL** varsa *timestr* bir NULL değil veya ayarlayın **errno**için **ERANGE** varsa *timestr* yanlış biçimlendirilmiş.

C++'da, bu işlevlerin daha yeni, güvenli ortaklarınıza çağırma şablon aşırı yüklemeleri bu işlevler vardır. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstrtime**|**_strtime**|**_strtime**|**_wstrtime**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_strtime**|\<time.h >|
|**_wstrtime**|\<time.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_strtime.c
// compile with: /W3

#include <time.h>
#include <stdio.h>

int main( void )
{
   char tbuffer [9];
   _strtime( tbuffer ); // C4996
   // Note: _strtime is deprecated; consider using _strtime_s instead
   printf( "The current time is %s \n", tbuffer );
}
```

```Output
The current time is 14:21:44
```

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Yönetimi](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[mktime, _mktime32, _mktime64](mktime-mktime32-mktime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_tzset](tzset.md)<br/>
