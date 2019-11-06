---
title: _strtime_s, _wstrtime_s
ms.date: 11/04/2016
api_name:
- _wstrtime_s
- _strtime_s
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: c74e7359f68469fd8322ba1c9348acffd636282a
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73625912"
---
# <a name="_strtime_s-_wstrtime_s"></a>_strtime_s, _wstrtime_s

Geçerli saati bir arabelleğe kopyalayın. Bu sürümler, [CRT 'Daki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleriyle birlikte [_wstrtime](strtime-wstrtime.md) .

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

*arabelleğin*<br/>
Saatin yazılacağı, en az 10 bayt uzunluğunda bir arabellek.

*numberOfElements*<br/>
Arabelleğin boyutu.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır.

Bir hata durumu oluşursa, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Hata varsa dönüş değeri bir hata kodudur. Hata kodları ERRNO içinde tanımlanmıştır. Olsun Bu işlev tarafından oluşturulan tam hatalar için aşağıdaki tabloya bakın. Hata kodları hakkında daha fazla bilgi için bkz. [errno sabitleri](../../c-runtime-library/errno-constants.md).

### <a name="error-conditions"></a>Hata koşulları

|*arabelleğin*|*numberOfElements*|döndürülmesini|*Arabelleğin* içeriği|
|--------------|------------------------|------------|--------------------------|
|**DEĞER**|kaydedilmemiş|**EıNVAL**|değiştirilmedi|
|**Null** değil (geçerli arabelleğe işaret ediyor)|0|**EıNVAL**|değiştirilmedi|
|**Null** değil (geçerli arabelleğe işaret ediyor)|0 < boyutu < 9|**EıNVAL**|Boş dize|
|**Null** değil (geçerli arabelleğe işaret ediyor)|Boyut > 9|0|Geçerli saat, açıklamalara belirtilen şekilde biçimlendirildi|

## <a name="security-issues"></a>Güvenlik Sorunları

*NumberOfElements* parametresi 9 ' dan büyükse, arabellek Için geçersiz**null** olmayan bir değer geçirmek erişim ihlaline neden olur.

Arabelleğin gerçek boyutundan daha büyük olan *numberOfElements* için değer geçirilmesi arabellek taşmasına neden olur.

## <a name="remarks"></a>Açıklamalar

Bu işlevler, [_strtime](strtime-wstrtime.md) ve [_wstrtime](strtime-wstrtime.md)'in daha güvenli sürümlerini sağlar. **_Strtime_s** işlevi, geçerli yerel saati *timestr*tarafından işaret edilen arabelleğe kopyalar. Süre SS **: DD: ss** olarak biçimlendirilir; burada **SS** , 24 saatlik gösterimde saati temsil eden iki haneye, **mm** , saati geçen dakikaları temsil eden iki haneye ve **nn** saniyeyi temsil eden iki haneye sahiptir. Örneğin, **18:23:44** dizesi 23 dakika ve 44 saniye içinde 6 P.M. temsil eder Arabellek en az 9 bayt uzunluğunda olmalıdır; Gerçek Boyut ikinci parametre ile belirtilir.

**_wstrtime** , **_strtime**öğesinin geniş karakterli bir sürümüdür; **_wstrtime** bağımsız değişkeni ve dönüş değeri geniş karakterli dizelerdir. Bu işlevler, aynı şekilde davranır.

' C++De, bu işlevlerin kullanılması şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkarabilir (bir boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırır) ve eski, güvenli olmayan işlevleri otomatik olarak yeni, güvenli karşılıklarıyla değiştirebilir. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

Bu işlevlerin hata ayıklama Kitaplığı sürümleri ilk olarak arabelleği 0xFE ile doldurur. Bu davranışı devre dışı bırakmak için [_Crtsetdebugfillthreshold](crtsetdebugfillthreshold.md)kullanın.

### <a name="generic-text-routine-mapping"></a>Genel metin rutin eşleme:

|TCHAR.H yordamı|_UNıCODE & _MBCS tanımlı değil|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstrtime_s**|**_strtime_s**|**_strtime_s**|**_wstrtime_s**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_strtime_s**|\<zaman. h >|
|**_wstrtime_s**|\<Time. h > veya \<wchar. h >|

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
