---
title: _strtime_s, _wstrtime_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- wstrtime_s function
- copying time to buffers
- strtime_s function
- _wstrtime_s function
- time, copying
- _strtime_s function
ms.assetid: 42acf013-c334-485d-b610-84c0af8a46ec
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a18b9ffe4fac351d73e0a78a6e25a71625a47b9e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="strtimes-wstrtimes"></a>_strtime_s, _wstrtime_s

Geçerli saati bir arabellek kopyalayın. Sürümleri bunlar [_strtime, _wstrtime](strtime-wstrtime.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

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

Bir hata koşulu ortaya çıkarsa, geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Bir hata olduğunda dönüş değeri bir hata kodudur. Hata kodları ERRNO içinde tanımlanmıştır. H; Bu işlev tarafından oluşturulan tam hatalar için aşağıdaki tabloya bakın. Hata kodları hakkında daha fazla bilgi için bkz: [errno sabitleri](../../c-runtime-library/errno-constants.md).

### <a name="error-conditions"></a>Hata koşulları

|*Arabellek*|*numberOfElements*|Döndür|İçeriği *arabellek*|
|--------------|------------------------|------------|--------------------------|
|**NULL**|(any)|**EINVAL**|değiştirilmedi|
|Değil **NULL** (geçerli arabelleğe işaret eden)|0|**EINVAL**|değiştirilmedi|
|Değil **NULL** (geçerli arabelleğe işaret eden)|0 < < 9 boyut|**EINVAL**|Boş dize|
|Değil **NULL** (geçerli arabelleğe işaret eden)|Boyut > 9|0|Açıklamalar belirtildiği gibi biçimlendirilmiş geçerli saati|

## <a name="security-issues"></a>Güvenlik sorunları

Arabellek bir erişim ihlali neden olur için geçersiz bir NULL olmayan değer geçirme *numberOfElements* parametredir 9 büyük.

Bir değer geçirmek için *numberOfElements* arabellek gerçek boyutuna arabellek taşması sonuçlanır daha büyük.

## <a name="remarks"></a>Açıklamalar

Bu işlevler daha güvenli sürümlerini sağlamak [_strtime](strtime-wstrtime.md) ve [_wstrtime](strtime-wstrtime.md). **_Strtime_s** işlevi geçerli yerel saat gösterdiği arabellek kopyalar *timestr*. Saat olarak biçimlendirilmiş **ss: dd:** nerede **hh** olan 24 saatlik gösteriminde saati temsil eden iki basamak **mm** olan saat ve geçetemsiledenikibasamak**ss** saniye temsil eden iki basamak değil. Örneğin, dize **18:23:44** 23 dakika ve 44 aşan saniye 6'da temsil eder Arabellek en az 9 bayt uzun olmalıdır; Gerçek Boyut ikinci parametresi tarafından belirtilir.

**_wstrtime** bir joker karakter sürümü **_strtime**; bağımsız değişkeni ve dönüş değeri **_wstrtime** joker karakter dizelerdir. Bu işlevler aynı şekilde aksi davranır.

C++'da, bu işlevler kullanılarak şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı arabellek uzunluğu otomatik olarak Infer (boyutu bağımsız değişkeniyle belirtme ihtiyacını ortadan) ve bunlar otomatik olarak yeni, güvenli dekiler ile daha eski, güvenli olmayan işlevleri değiştirebilirsiniz. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mapping"></a>Genel metin rutin eşleme:

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstrtime_s**|**_strtime_s**|**_strtime_s**|**_wstrtime_s**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_strtime_s**|\<time.h >|
|**_wstrtime_s**|\<time.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
