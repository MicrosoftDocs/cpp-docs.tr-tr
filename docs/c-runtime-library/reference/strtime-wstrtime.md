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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 827e5a579d801c12b932440fcbbaa18343ad7ece
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81316875"
---
# <a name="_strtime-_wstrtime"></a>_strtime, _wstrtime

Zamanı arabelleğe kopyalayın. Bu işlevlerin daha güvenli sürümleri mevcuttur; [_strtime_s, _wstrtime_s](strtime-s-wstrtime-s.md)bakın.

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

*keztr*<br/>
Zaman telli.

## <a name="return-value"></a>Dönüş Değeri

Bir işaretçiyi ortaya çıkan karakter dize *timestr'ına*döndürür.

## <a name="remarks"></a>Açıklamalar

**_strtime** işlevi, geçerli yerel saati *zamantr*tarafından işaret edilen arabelleğe kopyalar. Saat **hh:mm:ss olarak biçimlendirilir hh:mm:ss** **24** saatlik gösterimde saati temsil eden iki basamak, **mm** saati geçen dakikayı temsil eden iki basamak ve **ss** saniyeyi temsil eden iki basamaktır. Örneğin, **dize 18:23:44** 23 dakika ve 44 saniye 18:00 geçmiş temsil eder. Arabellek en az 9 bayt uzunluğunda olmalıdır.

**_wstrtime** **_strtime**geniş karakterli bir versiyonudur; _wstrtime bağımsız değişkeni **_wstrtime** ve geri dönüş değeri geniş karakterli dizeleridir. Bu işlevler aynı şekilde başka türlü çalışır. *Timestr* bir **NULL** işaretçisiyse veya *timestr* yanlış biçimlendirilmişse, geçersiz parametre işleyicisi [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Özel durum devam etmesine izin verilirse, *timestr* yanlış biçimlendirilmişse, bu **NULL** işlevler bir **NULL** döndürer ve **EINVAL'a** **ERANGE** *timestr* **errno** ayarlar. **errno**

C++'da, bu işlevlerin daha yeni ve güvenli karşıtlarını çağıran şablon aşırı yüklemeleri vardır. Daha fazla bilgi için Bkz. [Güvenli Şablon Overloads.](../../c-runtime-library/secure-template-overloads.md)

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstrtime**|**_strtime**|**_strtime**|**_wstrtime**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_strtime**|\<time.h>|
|**_wstrtime**|\<time.h> \<veya wchar.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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
