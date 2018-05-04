---
title: asctime_s, _wasctime_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wasctime_s
- asctime_s
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
- asctime_s
- _wasctime_s
- _tasctime_s
dev_langs:
- C++
helpviewer_keywords:
- tasctime_s function
- _tasctime_s function
- time structure conversion
- wasctime_s function
- time, converting
- _wasctime_s function
- asctime_s function
ms.assetid: 17ad9b2b-a459-465d-976a-42822897688a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4300d5fdab43cf4d22cf4e1fdee790f9d06d00d0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="asctimes-wasctimes"></a>asctime_s, _wasctime_s

Dönüştürme bir **tm** zaman bir karakter dizesine yapısı. Bu işlevler sürümleridir [asctime, _wasctime](asctime-wasctime.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Sözdizimi

```C
errno_t asctime_s(
   char* buffer,
   size_t numberOfElements,
   const struct tm *tmSource
);
errno_t _wasctime_s(
   wchar_t* buffer,
   size_t numberOfElements
   const struct tm *tmSource
);
template <size_t size>
errno_t asctime_s(
   char (&buffer)[size],
   const struct tm *tmSource
); // C++ only
template <size_t size>
errno_t _wasctime_s(
   wchar_t (&buffer)[size],
   const struct tm *tmSource
); // C++ only
```

### <a name="parameters"></a>Parametreler

*Arabellek*<br/>
Karakter dizesi sonucu depolamak için bir arabellek için bir işaretçi. Bu işlev tarafından belirtilen boyutta bir işaretçi bir geçerli bellek konumuna varsayar *numberOfElements*.

*numberOfElements*<br/>
Sonucu depolamak için kullanılan arabellek boyutu.

*tmSource*<br/>
Saat/tarih yapısı. Bu işlev geçerli bir işaretçi varsayar **yapısı** **tm** nesnesi.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır. Bir hata olduğunda geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, dönüş değeri bir hata kodudur. Hata kodları ERRNO içinde tanımlanmıştır. H. Daha fazla bilgi için bkz: [errno sabitleri](../../c-runtime-library/errno-constants.md). Her bir hata koşulu için döndürülen gerçek hata kodları aşağıdaki tabloda gösterilmektedir.

### <a name="error-conditions"></a>Hata koşulları

|*Arabellek*|*numberOfElements*|*tmSource*|Döndür|Değer *arabellek*|
|--------------|------------------------|----------|------------|-----------------------|
|**NULL**|tüm|tüm|**EINVAL**|değiştirilmedi|
|Değil **NULL** (noktaları için geçerli bellek)|0|tüm|**EINVAL**|değiştirilmedi|
|değil **NULL**|0 < < 26 boyutu|tüm|**EINVAL**|Boş dize|
|değil **NULL**|>= 26|**NULL**|**EINVAL**|Boş dize|
|değil **NULL**|>= 26|Geçersiz zaman yapısı veya aralık değerleri zamanı bileşenleri için yetersiz|**EINVAL**|Boş dize|

> [!NOTE]
> Hata koşulları için **wasctime_s** benzer **asctime_s** boyut sınırını sözcükleri ölçülür özel durum oluştu.

## <a name="remarks"></a>Açıklamalar

**Asctime** işlevi bir karakter dizesine yapısı olarak depolanan bir saat dönüştürür. *TmSource* değeri çağrısından alınan genellikle **gmtime** veya **damgasını**. Her iki işlevleri doldurmak için kullanılan bir **tm** zamanında tanımlandığı şekilde yapılandırın. H.

|timeptr üyesi|Değer|
|--------------------|-----------|
|**tm_hour**|Saat (0-23) gece yarısından|
|**tm_isdst**|Yaz Saati etkinse pozitif; Yaz Saati etkin değilse, 0; Yaz Saati durumunu bilinmiyorsa negatif. C çalışma zamanı kitaplığı, gün ışığından yararlanma saati (DST) hesaplama uygulamak için Amerika Birleşik Devletleri kuralları varsayar.|
|**tm_mday**|(1-31) ayın günü|
|**tm_min**|Dakika sonra saat (0-59)|
|**tm_mon**|Ay (0-11; Ocak = 0)|
|**tm_sec**|Dakika (0-59) saniye|
|**tm_wday**|Haftanın günü (0-6; Pazar = 0)|
|**tm_yday**|(0-365; yılın günü 1 Ocak = 0)|
|**tm_year**|Yıl (1900 eksi geçerli yıl)|

Dönüştürülen karakter dizesini de yerel saat dilimi ayarlarını göre ayarlanır. Bkz: [zamanı, _time32, _time64](time-time32-time64.md), [_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md), ve [localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md) işlevleri yapılandırma hakkında bilgi için yerel saat ve [_tzset](tzset.md) işlevi saat dilimi ortamı ve genel değişkenler tanımlama hakkında daha fazla bilgi için.

Tarafından üretilen dize sonuç **asctime_s** tam olarak 26 karakter içerir ve form `Wed Jan 02 02:03:55 1980\n\0`. 24 saatlik kullanılır. Tüm alanları sabit genişlik sahiptir. Yeni satır karakteri ve null karakter dizesi son iki konumlarını kaplar. İkinci parametre olarak geçirilen değer en az bu büyük olmalıdır. Bir hata kodu daha düşük ise **EINVAL**, döndürülür.

**_wasctime_s** bir joker karakter sürümü **asctime_s**. **_wasctime_s** ve **asctime_s** Aksi takdirde aynı şekilde davranır.

### <a name="generic-text-routine-mapping"></a>Genel metin rutin eşleme

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tasctime_s**|**asctime_s**|**asctime_s**|**_wasctime_s**|

C++'da, bu işlevler kullanılarak şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı, boyutu bağımsız değişkeniyle belirtme ihtiyacını ortadan arabellek uzunluğu bir otomatik olarak Infer. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**asctime_s**|\<time.h >|
|**_wasctime_s**|\<time.h > veya \<wchar.h >|

## <a name="security"></a>Güvenlik

Arabellek işaretçi değilse **NULL** ve işaretçiyi için geçerli bir arabellek göstermiyor, işlevi konumunda ne olursa olsun üzerine yazar. Bu ayrıca bir erişim ihlali neden olabilir.

A [taşması](http://msdn.microsoft.com/library/windows/desktop/ms717795) geçirilen boyutu bağımsız değişkeniyle arabellek gerçek boyutundan büyük ise oluşabilir.

## <a name="example"></a>Örnek

Bu program sistem saatini uzun tamsayı olarak yerleştirir **aclock**, yapısına çevirir **newtime** ve ardından dize form için çıktı, kullanarak **asctime_s**işlevi.

```C
// crt_asctime_s.c
#include <time.h>
#include <stdio.h>

struct tm newtime;
__time32_t aclock;

int main( void )
{
   char buffer[32];
   errno_t errNum;
   _time32( &aclock );   // Get time in seconds.
   _localtime32_s( &newtime, &aclock );   // Convert time to struct tm form.

   // Print local time as a string.

   errNum = asctime_s(buffer, 32, &newtime);
   if (errNum)
   {
       printf("Error code: %d", (int)errNum);
       return 1;
   }
   printf( "Current date and time: %s", buffer );
   return 0;
}
```

```Output
Current date and time: Wed May 14 15:30:17 2003
```

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Yönetimi](../../c-runtime-library/time-management.md)<br/>
[ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_tzset](tzset.md)<br/>
