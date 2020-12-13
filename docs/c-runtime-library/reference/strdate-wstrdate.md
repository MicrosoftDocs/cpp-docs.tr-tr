---
description: 'Hakkında daha fazla bilgi edinin: _strdate _wstrdate'
title: _strdate, _wstrdate
ms.date: 4/2/2020
api_name:
- _strdate
- _wstrdate
- _o__strdate
- _o__wstrdate
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _tstrdate
- wstrdate
- _wstrdate
- _strdate
- strdate
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
ms.openlocfilehash: 1e0daab087653edf57b3f268aa14192ab145cac6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340573"
---
# <a name="_strdate-_wstrdate"></a>_strdate, _wstrdate

Geçerli sistem tarihini bir arabelleğe kopyalayın. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz. [_strdate_s, _wstrdate_s](strdate-s-wstrdate-s.md).

## <a name="syntax"></a>Sözdizimi

```C
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

### <a name="parameters"></a>Parametreler

*batestr*<br/>
Biçimlendirilen Tarih dizesini içeren bir arabelleğin işaretçisi.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri, sonuçta elde *edilen dize karakter* dizesi için bir işaretçi döndürür.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz. [_strdate_s, _wstrdate_s](strdate-s-wstrdate-s.md). Mümkün olan yerlerde daha güvenli işlevlerin kullanılması önerilir.

**_Strdate** işlevi, geçerli sistem tarihini *ertestr* tarafından işaret edilen arabelleğe,  / **mm gg** / **yy**, yani **AA** de ayı temsil eden iki basamakla, **gg** günü temsil eden iki basamakla ve **yy** yılın son iki basamağından oluşur. Örneğin, **12/05/99** dizesi 5 Aralık 1999 ' i temsil eder. Arabellek en az 9 bayt uzunluğunda olmalıdır.

Eğer *davtestr* **null** Işaretçisiyse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler-1 döndürür ve **errno** , **EINVAL** olarak ayarlanır.

**_wstrdate** , **_strdate** geniş karakterli bir sürümüdür; **_wstrdate** bağımsız değişkeni ve dönüş değeri geniş karakterli dizelerdir. Bu işlevler, aynı şekilde davranır.

C++ ' da, bu işlevlerin, bu işlevlerin daha yeni ve güvenli bir şekilde çağrılmasını sağlayan şablon aşırı yüklemeleri vardır. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstrdate**|**_strdate**|**_strdate**|**_wstrdate**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_strdate**|\<time.h>|
|**_wstrdate**|\<time.h> veya \<wchar.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
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

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Yönetimi](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[mktime, _mktime32, _mktime64](mktime-mktime32-mktime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_tzset](tzset.md)<br/>
