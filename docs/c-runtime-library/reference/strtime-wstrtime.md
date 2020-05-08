---
title: _strtime, _wstrtime
ms.date: 4/2/2020
api_name:
- _wstrtime
- _strtime
- _o__strtime
- _o__wstrtime
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
ms.openlocfilehash: 7d9752ff9eb1fd7a4fa08c2a6ab89fefe456dad1
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82910916"
---
# <a name="_strtime-_wstrtime"></a>_strtime, _wstrtime

Süreyi bir arabelleğe kopyalayın. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz. [_strtime_s, _wstrtime_s](strtime-s-wstrtime-s.md).

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
Zaman dizesi.

## <a name="return-value"></a>Dönüş Değeri

Sonuç karakter dizesi *timestr*için bir işaretçi döndürür.

## <a name="remarks"></a>Açıklamalar

**_Strtime** işlevi, geçerli yerel saati *timestr*tarafından işaret edilen arabelleğe kopyalar. Süre SS **: DD: ss** olarak biçimlendirilir; burada **SS** , 24 saatlik gösterimde saati temsil eden iki haneye, **mm** , saati geçen dakikaları temsil eden iki haneye ve **nn** saniyeyi temsil eden iki haneye sahiptir. Örneğin, **18:23:44** dizesi 23 dakika ve 44 saniye içinde 6 P.M. temsil eder Arabellek en az 9 bayt uzunluğunda olmalıdır.

**_wstrtime** , **_strtime**geniş karakterli bir sürümüdür; **_wstrtime** bağımsız değişkeni ve dönüş değeri geniş karakterli dizelerdir. Bu işlevler, aynı şekilde davranır. *Timestr* **null** işaretçisiyse veya *timestr* yanlış biçimlendirildiyse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Özel durumun devam etmesine izin *timestr* veriliyorsa, bu işlevler **null** döndürür ve *timestr* **null** ise, errno olarak **EINVAL** **olarak ayarlanır** . **errno** **ERANGE**

C++ ' da, bu işlevlerin, bu işlevlerin daha yeni ve güvenli bir şekilde çağrılmasını sağlayan şablon aşırı yüklemeleri vardır. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstrtime**|**_strtime**|**_strtime**|**_wstrtime**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_strtime**|\<Time. h>|
|**_wstrtime**|\<Time. h> veya \<wchar. h>|

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
