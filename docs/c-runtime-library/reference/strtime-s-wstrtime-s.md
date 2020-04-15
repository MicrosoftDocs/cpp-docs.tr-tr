---
title: _strtime_s, _wstrtime_s
ms.date: 4/2/2020
api_name:
- _wstrtime_s
- _strtime_s
- _o__strtime_s
- _o__wstrtime_s
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 771dfdb6bd8035fe8683d62d52b3b4980ecda215
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81316931"
---
# <a name="_strtime_s-_wstrtime_s"></a>_strtime_s, _wstrtime_s

Geçerli saati arabelleğe kopyalayın. Bunlar, [CRT'deki](strtime-wstrtime.md) Güvenlik Özellikleri'nde açıklandığı gibi güvenlik geliştirmeleriyle _wstrtime _strtime [sürümleridir.](../../c-runtime-library/security-features-in-the-crt.md)

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
Bir arabellek, en az 10 bayt uzunluğunda, zaman yazılacak.

*numberOfElements*<br/>
Arabelleğe in boyutu.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır.

Bir hata koşulu oluşursa, geçersiz parametre işleyicisi, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. İade değeri, bir hata varsa bir hata kodudur. Hata kodları ERRNO'da tanımlanır. H; bu işlev tarafından oluşturulan tam hatalar için aşağıdaki tabloya bakın. Hata kodları hakkında daha fazla bilgi için [errno Sabitleri'ne](../../c-runtime-library/errno-constants.md)bakın.

### <a name="error-conditions"></a>Hata Koşulları

|*Arabellek*|*numberOfElements*|Dönüş|*Arabellek* içeriği|
|--------------|------------------------|------------|--------------------------|
|**Null**|(herhangi bir)|**Eınval**|Değiştirilmedi|
|**NULL** değil (geçerli arabelleği işaret eden)|0|**Eınval**|Değiştirilmedi|
|**NULL** değil (geçerli arabelleği işaret eden)|0 < boyutu < 9|**Eınval**|Boş dize|
|**NULL** değil (geçerli arabelleği işaret eden)|Boyut > 9|0|Açıklamalarta belirtildiği gibi biçimlendirilmiş geçerli zaman|

## <a name="security-issues"></a>Güvenlik Sorunları

Arabellek için geçersiz bir**NULL** olmayan değer in passing *numberOfElements* parametresi 9'dan büyükse bir erişim ihlaline neden olur.

Arabellek gerçek boyutundan büyük olan *numberOfElements* için bir değer geçirilmesi arabellek taşma neden olur.

## <a name="remarks"></a>Açıklamalar

Bu işlevler [_strtime](strtime-wstrtime.md) ve [_wstrtime](strtime-wstrtime.md)daha güvenli sürümlerini sağlar. **_strtime_s** işlevi, geçerli yerel saati *zamantr*tarafından işaret edilen arabelleğe kopyalar. Saat **hh:mm:ss olarak biçimlendirilir hh:mm:ss** **24** saatlik gösterimde saati temsil eden iki basamak, **mm** saati geçen dakikayı temsil eden iki basamak ve **ss** saniyeyi temsil eden iki basamaktır. Örneğin, **dize 18:23:44** 23 dakika ve 44 saniye 18:00 geçmiş temsil eder. Arabellek en az 9 bayt uzunluğunda olmalıdır; gerçek boyut ikinci parametre ile belirtilir.

**_wstrtime** **_strtime**geniş karakterli bir versiyonudur; _wstrtime bağımsız değişkeni **_wstrtime** ve geri dönüş değeri geniş karakterli dizeleridir. Bu işlevler aynı şekilde başka türlü çalışır.

C++'da, bu işlevleri kullanmak şablon aşırı yükleri ile basitleştirilir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkartabilir (boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırabilir) ve eski, güvenli olmayan işlevleri yeni, güvenli karşılıklarıyla otomatik olarak değiştirebilirler. Daha fazla bilgi için Bkz. [Güvenli Şablon Overloads.](../../c-runtime-library/secure-template-overloads.md)

Bu işlevlerin hata ayıklama kitaplığı sürümleri önce arabelleği 0xFE ile doldurur. Bu davranışı devre dışı kullanabilirsiniz, [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md)kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mapping"></a>Genel Metin Rutin Eşleme:

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstrtime_s**|**_strtime_s**|**_strtime_s**|**_wstrtime_s**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_strtime_s**|\<time.h>|
|**_wstrtime_s**|\<time.h> \<veya wchar.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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
