---
title: _strdate, _wstrdate
ms.date: 11/04/2016
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
ms.openlocfilehash: 4dc2ea7f25e644c9bf7a4ddca4a625991f37d912
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62353969"
---
# <a name="strdate-wstrdate"></a>_strdate, _wstrdate

Geçerli sistem tarihini arabelleğe kopyalayın. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz: [_strdate_s, _wstrdate_s](strdate-s-wstrdate-s.md).

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

*datestr*<br/>
Biçimlendirilen tarih dizesi içeren arabellek için işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri işaretçi için elde edilen karakter dizesi döndüren *datestr*.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz: [_strdate_s, _wstrdate_s](strdate-s-wstrdate-s.md). Mümkünse daha güvenli işlevler kullanılması önerilir.

**_Strdate** işlevi tarafından işaret edilen arabellek için geçerli sistem tarihini kopyalar *datestr*biçimlendirilmiş **mm**/**GG** / **yy**burada **mm** olan ayı temsil eden iki basamak **GG** olan iki basamak gününü ve **yy**  yılın son iki basamak. Örneğin, dize **12/05/99** 5 Aralık 1999 temsil eder. Arabelleğin en az 9 bayt uzunluğunda olmalıdır.

Varsa *datestr* olduğu bir **NULL** işaretçiyse, geçersiz parametre işleyicisi çağrılır, açıklandığı [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, bu işlevler -1 döndürür ve **errno** için **EINVAL**.

**_wstrdate** geniş karakterli sürümüdür **_strdate**; bağımsız değişkeni ve dönüş değeri **_wstrdate** geniş karakterli dizelerdir. Bu işlevler, aynı şekilde davranır.

C++'da, bu işlevler, bu işlevlerin daha yeni ve güvenli karşılıklarını çağırma şablon aşırı yüklemeleri vardır. Daha fazla bilgi için [güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstrdate**|**_strdate**|**_strdate**|**_wstrdate**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_strdate**|\<TIME.h >|
|**_wstrdate**|\<TIME.h > veya \<wchar.h >|

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
