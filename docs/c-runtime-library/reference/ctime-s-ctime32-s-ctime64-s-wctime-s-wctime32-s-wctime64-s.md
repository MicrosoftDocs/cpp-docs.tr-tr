---
title: ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s
ms.date: 4/2/2020
api_name:
- _ctime64_s
- _wctime32_s
- ctime_s
- _wctime64_s
- _ctime32_s
- _wctime_s
- _o__ctime32_s
- _o__ctime64_s
- _o__wctime32_s
- _o__wctime64_s
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
- ctime64_s
- _ctime32_s
- _tctime32_s
- _ctime64_s
- _wctime_s
- _tctime_s
- _tctime64_s
- ctime_s
- ctime32_s
helpviewer_keywords:
- _wctime32_s function
- ctime64_s function
- _tctime64_s function
- _wctime_s function
- tctime_s function
- _wctime64_s function
- ctime_s function
- ctime32_s function
- _ctime64_s function
- tctime64_s function
- wctime64_s function
- wctime_s function
- _tctime_s function
- tctime32_s function
- wctime32_s function
- time, converting
- _ctime32_s function
- _tctime32_s function
ms.assetid: 36ac419a-8000-4389-9fd8-d78b747a009b
ms.openlocfilehash: d5121c795ed27c22d20087868f798a4b7f5f5b02
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348160"
---
# <a name="ctime_s-_ctime32_s-_ctime64_s-_wctime_s-_wctime32_s-_wctime64_s"></a>ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s

Bir saat değerini dize dönüştürün ve yerel saat dilimi ayarları için ayarlayın. Bunlar [CRT](../../c-runtime-library/security-features-in-the-crt.md)Güvenlik Özellikleri açıklandığı gibi güvenlik geliştirmeleri ile [_wctime64 ctime, _ctime64, _wctime](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md) sürümleridir.

## <a name="syntax"></a>Sözdizimi

```C
errno_t ctime_s(
   char* buffer,
   size_t numberOfElements,
   const time_t *sourceTime
);
errno_t _ctime32_s(
   char* buffer,
   size_t numberOfElements,
   const __time32_t *sourceTime
);
errno_t _ctime64_s(
   char* buffer,
   size_t numberOfElements,
   const __time64_t *sourceTime )
;
errno_t _wctime_s(
   wchar_t* buffer,
   size_t numberOfElements,
   const time_t *sourceTime
);
errno_t _wctime32_s(
   wchar_t* buffer,
   size_t numberOfElements,
   const __time32_t *sourceTime
);
errno_t _wctime64_s(
   wchar_t* buffer,
   size_t numberOfElements,
   const __time64_t *sourceTime
);
```

```cpp
template <size_t size>
errno_t _ctime32_s(
   char (&buffer)[size],
   const __time32_t *sourceTime
); // C++ only
template <size_t size>
errno_t _ctime64_s(
   char (&buffer)[size],
   const __time64_t *sourceTime
); // C++ only
template <size_t size>
errno_t _wctime32_s(
   wchar_t (&buffer)[size],
   const __time32_t *sourceTime
); // C++ only
template <size_t size>
errno_t _wctime64_s(
   wchar_t (&buffer)[size],
   const __time64_t *sourceTime
); // C++ only
```

### <a name="parameters"></a>Parametreler

*Arabellek*<br/>
26 karakter tutacak kadar büyük olmalı. Karakter dizesi sonucuna işaretçi veya aşağıdakileri varsa **NULL:**

- *sourceTime* gece yarısından önceki bir tarihi temsil eder, 1 Ocak 1970, UTC.

- **_ctime32_s** veya **_wctime32_s** kullanıyorsanız ve *sourceTime* 23:59:59 18 Ocak 2038, UTC'den sonraki bir tarihi temsil eder.

- **_ctime64_s** veya **_wctime64_s** kullanıyorsanız ve *sourceTime* 23:59:59, 31 Aralık 3000, UTC'den sonraki bir tarihi temsil eder.

- **_ctime_s** veya **_wctime_s**kullanıyorsanız, bu işlevler önceki işlevlere sarıcıdır. Açıklamalar bölümüne bakın.

*numberOfElements*<br/>
Arabelleğe in boyutu.

*kaynakZaman*<br/>
Zaman depolanan işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır. Geçersiz bir parametre nedeniyle bir hata varsa, geçersiz parametre işleyicisi, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmenin devam etmesine izin verilirse, bir hata kodu döndürülür. Hata kodları ERRNO'da tanımlanır. H; bu hataların bir listesi için, [bkz.](../../c-runtime-library/errno-constants.md) Her hata koşulu için atılan gerçek hata kodları aşağıdaki tabloda gösterilir.

## <a name="error-conditions"></a>Hata Koşulları

|*Arabellek*|*numberOfElements*|*kaynakZaman*|Dönüş|*Arabellekteki* değer|
|--------------|------------------------|------------|------------|-----------------------|
|**Null**|herhangi bir|herhangi bir|**Eınval**|Değiştirilmedi|
|**NULL** değil (geçerli belleğe işaret)|0|herhangi bir|**Eınval**|Değiştirilmedi|
|**NULL** değil|0< boyutu < 26|herhangi bir|**Eınval**|Boş dize|
|**NULL** değil|>= 26|NULL|**Eınval**|Boş dize|
|**NULL** değil|>= 26|< 0|**Eınval**|Boş dize|

## <a name="remarks"></a>Açıklamalar

**ctime_s** [işlevi, time_t](../../c-runtime-library/standard-types.md) yapısı olarak depolanan bir zaman değerini bir karakter dizesine dönüştürür. *SourceTime* değeri genellikle gece yarısından [time](time-time32-time64.md)(00:00:00), 1 Ocak 1970, eşgüdümlü evrensel saat (UTC) bu yana geçen saniye sayısını döndüren zaman aramadan elde edilir. İade değeri dizesi tam olarak 26 karakter içerir ve forma sahiptir:

`Wed Jan 02 02:03:55 1980\n\0`

24 saatlik bir saat kullanılır. Tüm alanların sabit bir genişliği vardır. Yeni satır karakteri ('\n') ve null karakter ('\0') dizesinin son iki pozisyonlarını kaplar.

Dönüştürülen karakter dizesi de yerel saat dilimi ayarlarına göre ayarlanır. Yerel saati ve [_tzset](tzset.md) işlevini yapılandırma hakkında bilgi için [saat,](time-time32-time64.md) [_ftime](ftime-ftime32-ftime64.md)ve [localtime32_s](localtime-s-localtime32-s-localtime64-s.md) işlevlerine bakın ve saat dilimi ortamını ve genel değişkenleri tanımlama hakkında bilgi için.

**_wctime32_s** ve **_wctime64_s** **_ctime32_s** ve **_ctime64_s**geniş karakterli versiyonu; geniş karakter dizesine bir işaretçi döndürme. Aksi takdirde, **_ctime64_s**, **_wctime32_s**, ve **_wctime64_s** **_ctime32_s**aynı şekilde davranan .

**ctime_s** **_ctime64_s** değerlendiren bir satır dışı işlevdir ve **time_t** **__time64_t**eşdeğerdir. Derleyiciyi **time_t** eski 32 bit **time_t**olarak yorumlamaya zorlamanız gerekiyorsa, **_USE_32BIT_TIME_T**tanımlayabilirsiniz. Bunu yapmak **ctime_s** **_ctime32_s**için değerlendirmeye neden olur. Başvurunuz 18 Ocak 2038'den sonra başarısız olabileceğinden ve 64 bit platformlarda izin verilmediği için bu önerilmez.

C++'da, bu işlevleri kullanmak şablon aşırı yükleri ile basitleştirilir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkararak boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırabilir. Daha fazla bilgi için Bkz. [Güvenli Şablon Overloads.](../../c-runtime-library/secure-template-overloads.md)

Bu işlevlerin hata ayıklama kitaplığı sürümleri önce arabelleği 0xFE ile doldurur. Bu davranışı devre dışı kullanabilirsiniz, [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md)kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tctime_s**|**ctime_s**|**ctime_s**|**_wctime_s**|
|**_tctime32_s**|**_ctime32_s**|**_ctime32_s**|**_wctime32_s**|
|**_tctime64_s**|**_ctime64_s**|**_ctime64_s**|**_wctime64_s**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**ctime_s**, **_ctime32_s**, **_ctime64_s**|\<time.h>|
|**_wctime_s**, **_wctime32_s**, **_wctime64_s**|\<time.h> \<veya wchar.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="libraries"></a>Kitaplıklar

C çalışma [zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="example"></a>Örnek

```C
// crt_wctime_s.c
// This program gets the current
// time in time_t form and then uses _wctime_s to
// display the time in string form.

#include <time.h>
#include <stdio.h>

#define SIZE 26

int main( void )
{
   time_t ltime;
   wchar_t buf[SIZE];
   errno_t err;

   time( &ltime );

   err = _wctime_s( buf, SIZE, &ltime );
   if (err != 0)
   {
      printf("Invalid Arguments for _wctime_s. Error Code: %d\n", err);
   }
   wprintf_s( L"The time is %s\n", buf );
}
```

```Output
The time is Fri Apr 25 13:03:39 2003
```

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Yönetimi](../../c-runtime-library/time-management.md)<br/>
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)<br/>
[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
