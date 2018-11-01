---
title: ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s
ms.date: 11/04/2016
apiname:
- _ctime64_s
- _wctime32_s
- ctime_s
- _wctime64_s
- _ctime32_s
- _wctime_s
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
ms.openlocfilehash: 0410aeda4bbec33738d01a9514181c19f351e2c4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50496385"
---
# <a name="ctimes-ctime32s-ctime64s-wctimes-wctime32s-wctime64s"></a>ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s

Bir zaman değeri dizeye Dönüştür ve yerel saat dilimi ayarlarını yapın. Bunlar sürümleridir [ctime, _ctime64, _wctime64 olan _wctime](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

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
26 karakter tutabilecek kadar büyük olmalıdır. Karakter dize sonucu için bir işaretçi veya **NULL** varsa:

- *sourceTime* 1 Ocak 1970 gece yarısı UTC tarihi temsil eder.

- Kullanırsanız **_ctime32_s** veya **_wctime32_s** ve *sourceTime* 23:59:59 18 Ocak 2038, UTC tarihinden temsil eder.

- Kullanırsanız **_ctime64_s** veya **_wctime64_s** ve *sourceTime* 23:59:59, 31 Aralık, 3000, UTC tarihinden temsil eder.

- Kullanırsanız **_ctime_s** veya **_wctime_s**, önceki işlevlere sarmalayıcıları bu işlevlerdir. Açıklamalar bölümüne bakın.

*numberOfElements*<br/>
Arabellek boyutu.

*sourceTime*<br/>
Depolanan zamana yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır. Geçersiz bir parametre nedeniyle bir hata varsa, geçersiz parametre işleyicisi açıklandığı gibi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin, bir hata kodu döndürülür. Hata kodları ERRNO içinde tanımlanır. H; Bu hataların bir listesi için bkz: [errno](../../c-runtime-library/errno-constants.md). Aşağıdaki tabloda her bir hata koşulu için oluşturulan gerçek hata kodları gösterilir.

## <a name="error-conditions"></a>Hata koşulları

|*Arabellek*|*numberOfElements*|*sourceTime*|döndürülecek|Değerini *arabelleği*|
|--------------|------------------------|------------|------------|-----------------------|
|**NULL**|Tüm|Tüm|**EINVAL**|değiştirilmedi|
|Değil **NULL** (geçerli bellek noktaları)|0|Tüm|**EINVAL**|değiştirilmedi|
|Değil **NULL**|0 < < 26 boyutu|Tüm|**EINVAL**|Boş dize|
|Değil **NULL**|>= 26|NULL|**EINVAL**|Boş dize|
|Değil **NULL**|>= 26|< 0|**EINVAL**|Boş dize|

## <a name="remarks"></a>Açıklamalar

**Ctime_s** işlevi olarak depolanan bir saat değerine dönüştürür bir [time_t](../../c-runtime-library/standard-types.md) yapısına göre bir karakter dizesi. *SourceTime* değeri çağrısından alınan genellikle [zaman](time-time32-time64.md), saniye cinsinden gece yarısından beri geçen döndüren (00: 00:00), 1 Ocak 1970, Eşgüdümlü Evrensel Saat (UTC). Dönüş değeri dize, tam olarak 26 karakterler içeriyor ve biçime sahiptir:

`Wed Jan 02 02:03:55 1980\n\0`

24 saatlik düzende kullanılır. Tüm alanlar, sabit bir genişliğe sahiptir. Yeni satır karakteri ('\n') ve null karakteri ('\0'), son iki dize konumlarını kaplar.

Dönüştürülmüş karakteri dize ayrıca yerel saat dilimi ayarlarını göre ayarlanır. Bkz: [zaman](time-time32-time64.md), [_ftime](ftime-ftime32-ftime64.md), ve [localtime32_s](localtime-s-localtime32-s-localtime64-s.md) yerel saat yapılandırma hakkında daha fazla bilgi için İşlevler ve [_tzset](tzset.md) Genel değişkenler ve saat dilimi ortamı tanımlama hakkında bilgi için işlev.

**_wctime32_s** ve **_wctime64_s** geniş karakter sürümüne sahip **_ctime32_s** ve **_ctime64_s**; geniş karakter dizesine bir işaretçi döndürüyor. Aksi takdirde, **_ctime64_s**, **_wctime32_s**, ve **_wctime64_s** öğesine aynı şekilde davranır **_ctime32_s**.

**ctime_s** olarak değerlendirilen bir satır içi işlevdir **_ctime64_s** ve **time_t** eşdeğerdir **__time64_t**. Yorumlamak üzere zorlamanız gerekirse **time_t** eski 32-bit olarak **time_t**, tanımlayabileceğiniz **_use_32bıt_tıme_t**. Bunun yapılması neden olacak **ctime_s** için değerlendirilecek **_ctime32_s**. Bu, 18 Ocak 2038 sonrasında uygulamanız çalışmayabilir ve 64-bit platformlarda izin verilmiyor çünkü önerilmez.

C++ dilinde bu işlevlerin kullanılması şablon aşırı yüklemeleriyle basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğu bir boyut bağımsız değişkeni belirtme gereksinimi ortadan otomatik olarak çıkarabilir. Daha fazla bilgi için [güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tctime_s**|**ctime_s**|**ctime_s**|**_wctime_s**|
|**_tctime32_s**|**_ctime32_s**|**_ctime32_s**|**_wctime32_s**|
|**_tctime64_s**|**_ctime64_s**|**_ctime64_s**|**_wctime64_s**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**ctime_s**, **_ctime32_s**, **_ctime64_s**|\<TIME.h >|
|**_wctime_s**, **_wctime32_s**, **_wctime64_s**|\<TIME.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

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
