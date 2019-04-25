---
title: _strtime, _wstrtime
ms.date: 11/04/2016
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
ms.openlocfilehash: 9d874321418854a703886eb80ee23ac1cba57fa4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62223104"
---
# <a name="strtime-wstrtime"></a>_strtime, _wstrtime

Zaman bir arabelleğe kopyalayın. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz: [_strtime_s, _wstrtime_s](strtime-s-wstrtime-s.md).

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

Sonuçta elde edilen karakter dizesine bir işaretçi döndürür *timestr*.

## <a name="remarks"></a>Açıklamalar

**_Strtime** işlevi geçerli yerel saat işaret ettiği arabelleğine kopyalar *timestr*. Saat olarak biçimlendirilmiş **ss: dd:** burada **hh** olduğu saat, 24 saatlik gösterimde temsil eden iki basamak **mm** olan saat ve geçetemsiledenikibasamak**ss** olduğu saniye temsil eden iki basamak. Örneğin, dize **18:23:44** 23 dakika ve 44 saniye 6'da geçmiş temsil eder Arabelleğin en az 9 bayt uzunluğunda olmalıdır.

**_wstrtime** geniş karakterli sürümüdür **_strtime**; bağımsız değişkeni ve dönüş değeri **_wstrtime** geniş karakterli dizelerdir. Bu işlevler, aynı şekilde davranır. Varsa *timestr* olduğu bir **NULL** işaretçi veya *timestr* yanlış, geçersiz biçimlendirilmiş parametre işleyicisi çağrılır, açıklandığı [parametresi Doğrulama](../../c-runtime-library/parameter-validation.md). Özel durumun devam etmesine izin verilirse, bu işlevler döndürür bir **NULL** ayarlayıp **errno** için **EINVAL** varsa *timestr* bir olan**NULL** veya **errno** için **ERANGE** varsa *timestr* yanlış biçimlendirilmiş.

C++'da, bu işlevler, bu işlevlerin daha yeni ve güvenli karşılıklarını çağırma şablon aşırı yüklemeleri vardır. Daha fazla bilgi için [güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstrtime**|**_strtime**|**_strtime**|**_wstrtime**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_strtime**|\<TIME.h >|
|**_wstrtime**|\<TIME.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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
