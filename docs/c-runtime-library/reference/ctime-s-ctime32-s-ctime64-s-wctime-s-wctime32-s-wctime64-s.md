---
title: ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
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
caps.latest.revision: 27
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9d598ab0ef9aa2509e68e768182568870eb85e5d
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="ctimes-ctime32s-ctime64s-wctimes-wctime32s-wctime64s"></a>ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s

Bir saat değeri dizeye ve yerel saat dilimi ayarlarını yapın. Sürümleri bunlar [ctime, _ctime64, _wctime, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

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
26 karakter tutabilecek kadar büyük olmalıdır. Karakter dizesi sonucu için bir işaretçi veya **NULL** varsa:

- *sourceTime* gece, 1 Ocak 1970 UTC tarihi temsil eder.

- Kullanırsanız **_ctime32_s** veya **_wctime32_s** ve *sourceTime* 23:59:59 18 Ocak 2038, UTC tarihinden temsil eder.

- Kullanırsanız **_ctime64_s** veya **_wctime64_s** ve *sourceTime* 23:59:59 31 Aralık 3000 UTC tarihinden temsil eder.

- Kullanırsanız **_ctime_s** veya **_wctime_s**, önceki işlevlere sarmalayıcıları bu işlevlerdir. Açıklamalar bölümüne bakın.

*numberOfElements*<br/>
Arabellek boyutu.

*sourceTime*<br/>
Saklı zaman işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır. Geçersiz bir parametre nedeniyle bir hata olduğunda geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bir hata kodu döndürdü. Hata kodları ERRNO içinde tanımlanmıştır. H; Bu hataların listesi için bkz: [errno](../../c-runtime-library/errno-constants.md). Her bir hata koşulu için oluşturulan gerçek hata kodları aşağıdaki tabloda gösterilmektedir.

## <a name="error-conditions"></a>Hata koşulları

|*Arabellek*|*numberOfElements*|*sourceTime*|Döndür|Değer *arabellek*|
|--------------|------------------------|------------|------------|-----------------------|
|**NULL**|tüm|tüm|**EINVAL**|değiştirilmedi|
|Değil **NULL** (noktaları için geçerli bellek)|0|tüm|**EINVAL**|değiştirilmedi|
|değil **NULL**|0 < < 26 boyutu|tüm|**EINVAL**|Boş dize|
|değil **NULL**|>= 26|NULL|**EINVAL**|Boş dize|
|değil **NULL**|>= 26|< 0|**EINVAL**|Boş dize|

## <a name="remarks"></a>Açıklamalar

**Ctime_s** işlevi dönüştürür olarak saklanan bir saat değeri bir [time_t](../../c-runtime-library/standard-types.md) yapısı içinde bir karakter dizesi. *SourceTime* değeri çağrısından alınan genellikle [zaman](time-time32-time64.md), gece yarısından beri geçen saniye sayısı döndüren (00: 00:00), 1 Ocak 1970'den itibaren Eşgüdümlü Evrensel Saat (UTC). Dönüş değeri dize tam olarak 26 karakter içerir ve biçime sahiptir:

`Wed Jan 02 02:03:55 1980\n\0`

24 saatlik kullanılır. Tüm alanları sabit genişlik sahiptir. Yeni satır karakteri ('\n') ve ('\0') null karakter dizesi son iki konumlarını kaplar.

Dönüştürülen karakter dizesini de yerel saat dilimi ayarlarını göre ayarlanır. Bkz: [zaman](time-time32-time64.md), [_ftime](ftime-ftime32-ftime64.md), ve [localtime32_s](localtime-s-localtime32-s-localtime64-s.md) yerel saat yapılandırma hakkında bilgi için İşlevler ve [_tzset](tzset.md) saat dilimi ortamı ve genel değişkenler tanımlama hakkında daha fazla bilgi için işlevi.

**_wctime32_s** ve **_wctime64_s** joker karakter sürümüne sahip **_ctime32_s** ve **_ctime64_s**; joker karakter dizesi için bir işaretçi döndürüyor. Aksi takdirde, **_ctime64_s**, **_wctime32_s**, ve **_wctime64_s** aynı şekilde davranır **_ctime32_s**.

**ctime_s** değerlendiren bir satır içi işlev **_ctime64_s** ve **time_t** eşdeğerdir **__time64_t**. Yorumlamaya derleyici zorlamak gerekiyorsa **time_t** eski 32 bit olarak **time_t**, tanımlayabileceğiniz **_USE_32BIT_TIME_T**. Bunun neden olacak **ctime_s** için değerlendirilecek **_ctime32_s**. Bu, uygulamanızın 18 Ocak 2038 sonra başarısız olabilir ve 64 bit platformlarda izin verilmiyor çünkü önerilmez.

C++'da, bu işlevler kullanılarak şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı, boyutu bağımsız değişkeniyle belirtme ihtiyacını ortadan arabellek uzunluğu bir otomatik olarak Infer. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tctime_s**|**ctime_s**|**ctime_s**|**_wctime_s**|
|**_tctime32_s**|**_ctime32_s**|**_ctime32_s**|**_wctime32_s**|
|**_tctime64_s**|**_ctime64_s**|**_ctime64_s**|**_wctime64_s**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**ctime_s**, **_ctime32_s**, **_ctime64_s**|\<time.h >|
|**_wctime_s**, **_wctime32_s**, **_wctime64_s**|\<time.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
