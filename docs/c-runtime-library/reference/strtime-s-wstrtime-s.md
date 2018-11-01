---
title: _strtime_s, _wstrtime_s
ms.date: 11/04/2016
apiname:
- _wstrtime_s
- _strtime_s
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
- _wstrtime_s
- strtime_s
- wstrtime_s
- _strtime_s
helpviewer_keywords:
- wstrtime_s function
- copying time to buffers
- strtime_s function
- _wstrtime_s function
- time, copying
- _strtime_s function
ms.assetid: 42acf013-c334-485d-b610-84c0af8a46ec
ms.openlocfilehash: 579c4a99b52c66bd14cea947eaa1f301cc1127e1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50642370"
---
# <a name="strtimes-wstrtimes"></a>_strtime_s, _wstrtime_s

Geçerli saatten bir arabelleğe kopyalayın. Bunlar sürümleridir [_strtime, _wstrtime](strtime-wstrtime.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Sözdizimi

```C
errno_t _strtime_s(
   char *buffer,
   size_t numberOfElements
);
errno_t _wstrtime_s(
   wchar_t *buffer,
   size_t numberOfElements
);
template <size_t size>
errno_t _strtime_s(
   char (&buffer)[size]
); // C++ only
template <size_t size>
errno_t _wstrtime_s(
   wchar_t (&buffer)[size]
); // C++ only
```

### <a name="parameters"></a>Parametreler

*Arabellek*<br/>
Zaman yazılacağı bir arabellek, en az 10 bayt uzun.

*numberOfElements*<br/>
Arabellek boyutu.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır.

Bir hata koşulu ortaya çıkarsa, geçersiz parametre açıklandığı gibi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Bir hata varsa dönüş değeri bir hata kodudur. Hata kodları ERRNO içinde tanımlanır. H; Bu işlev tarafından oluşturulan tam hatalar için aşağıdaki tabloya bakın. Hata kodları hakkında daha fazla bilgi için bkz. [errno sabitleri](../../c-runtime-library/errno-constants.md).

### <a name="error-conditions"></a>Hata koşulları

|*Arabellek*|*numberOfElements*|döndürülecek|İçeriğini *arabelleği*|
|--------------|------------------------|------------|--------------------------|
|**NULL**|(any)|**EINVAL**|değiştirilmedi|
|Değil **NULL** (geçerli arabelleğe işaret eden)|0|**EINVAL**|değiştirilmedi|
|Değil **NULL** (geçerli arabelleğe işaret eden)|0 < < 9 boyutu|**EINVAL**|Boş dize|
|Değil **NULL** (geçerli arabelleğe işaret eden)|Boyut > 9|0|Açıklamalar belirtildiği gibi biçimlendirilmiş olarak geçerli saati|

## <a name="security-issues"></a>Güvenlik Sorunları

Geçersiz bir olmayan geçirme**NULL** arabellek, erişim ihlali ile sonuçlanacak değer *numberOfElements* parametresi, 9'dan büyük.

Bir değer geçirmek için *numberOfElements* arabellek gerçek boyutu arabellek taşmasına neden olur, daha büyük.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin daha güvenli sürümleri sağlamak [_strtime](strtime-wstrtime.md) ve [_wstrtime](strtime-wstrtime.md). **_Strtime_s** işlevi geçerli yerel saat işaret ettiği arabelleğine kopyalar *timestr*. Saat olarak biçimlendirilmiş **ss: dd:** burada **hh** olduğu saat, 24 saatlik gösterimde temsil eden iki basamak **mm** olan saat ve geçetemsiledenikibasamak**ss** olduğu saniye temsil eden iki basamak. Örneğin, dize **18:23:44** 23 dakika ve 44 saniye 6'da geçmiş temsil eder Arabelleğin en az 9 bayt uzunluğunda olmalıdır; Gerçek boyut, ikinci parametre belirtilir.

**_wstrtime** geniş karakterli sürümüdür **_strtime**; bağımsız değişkeni ve dönüş değeri **_wstrtime** geniş karakterli dizelerdir. Bu işlevler, aynı şekilde davranır.

C++ dilinde bu işlevlerin kullanılması şablon aşırı yüklemeleriyle basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkarabilir (bir boyut bağımsız değişkeni belirtme gereksinimi ortadan kalkar) ve bunlar otomatik olarak eski ve güvenli olmayan işlevlerle daha yeni ve güvenli karşılıklarını değiştirir. Daha fazla bilgi için [güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mapping"></a>Genel metin yordam eşlemesi:

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstrtime_s**|**_strtime_s**|**_strtime_s**|**_wstrtime_s**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_strtime_s**|\<TIME.h >|
|**_wstrtime_s**|\<TIME.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// strtime_s.c

#include <time.h>
#include <stdio.h>

int main()
{
    char tmpbuf[9];
    errno_t err;

    // Set time zone from TZ environment variable. If TZ is not set,
    // the operating system is queried to obtain the default value
    // for the variable.
    //
    _tzset();

    // Display operating system-style date and time.
    err = _strtime_s( tmpbuf, 9 );
    if (err)
    {
       printf("_strdate_s failed due to an invalid argument.");
      exit(1);
    }
    printf( "OS time:\t\t\t\t%s\n", tmpbuf );
    err = _strdate_s( tmpbuf, 9 );
    if (err)
    {
       printf("_strdate_s failed due to an invalid argument.");
       exit(1);
    }
    printf( "OS date:\t\t\t\t%s\n", tmpbuf );

}
```

```Output
OS time:            14:37:49
OS date:            04/25/03
```

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Yönetimi](../../c-runtime-library/time-management.md)<br/>
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)<br/>
[ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)<br/>
[mktime, _mktime32, _mktime64](mktime-mktime32-mktime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_tzset](tzset.md)<br/>
