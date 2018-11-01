---
title: asctime_s, _wasctime_s
ms.date: 11/04/2016
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
helpviewer_keywords:
- tasctime_s function
- _tasctime_s function
- time structure conversion
- wasctime_s function
- time, converting
- _wasctime_s function
- asctime_s function
ms.assetid: 17ad9b2b-a459-465d-976a-42822897688a
ms.openlocfilehash: 350d8c7b1dcf61272a3cfee884dff8a63b455f1c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50471961"
---
# <a name="asctimes-wasctimes"></a>asctime_s, _wasctime_s

Dönüştürme bir **tm** zaman yapısı için bir karakter dizesi. Bu işlevlerin sürümleri şunlardır: [asctime, _wasctime](asctime-wasctime.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

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
Karakter dize sonucu depolamak için arabellek için işaretçi. Bu işlev tarafından belirtilen boyutta bir işaretçi geçerli bellek konumuna varsayar *numberOfElements*.

*numberOfElements*<br/>
Sonucu depolamak için kullanılan arabellek boyutu.

*tmSource*<br/>
Saat/tarih yapısı. Bu işlev geçerli bir işaretçi varsayar **yapı** **tm** nesne.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır. Bir hata varsa, geçersiz parametre işleyicisi açıklandığı gibi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin, dönüş değeri bir hata kodudur. Hata kodları ERRNO içinde tanımlanır. H Daha fazla bilgi için [errno sabitleri](../../c-runtime-library/errno-constants.md). Aşağıdaki tabloda her bir hata koşulu için döndürülen gerçek hata kodları gösterilir.

### <a name="error-conditions"></a>Hata koşulları

|*Arabellek*|*numberOfElements*|*tmSource*|döndürülecek|Değerini *arabelleği*|
|--------------|------------------------|----------|------------|-----------------------|
|**NULL**|Tüm|Tüm|**EINVAL**|değiştirilmedi|
|Değil **NULL** (geçerli bellek noktaları)|0|Tüm|**EINVAL**|değiştirilmedi|
|Değil **NULL**|0 < < 26 boyutu|Tüm|**EINVAL**|Boş dize|
|Değil **NULL**|>= 26|**NULL**|**EINVAL**|Boş dize|
|Değil **NULL**|>= 26|Geçersiz zaman yapısı veya aralık değerleri zaman bileşenleri için yetersiz|**EINVAL**|Boş dize|

> [!NOTE]
> Hata koşulları için **wasctime_s** benzer **asctime_s** durumla boyut sınırını sözcükleri ölçülür.

## <a name="remarks"></a>Açıklamalar

**Asctime** işlevi dönüştürür bir yapıya bir karakter dizesi olarak depolanan bir süre. *TmSource* değeri çağrısından alınan genellikle **gmtime** veya **localtime**. Her iki işlev doldurmak için kullanılan bir **tm** , zaman içinde tanımlandığı şekilde yapılandırın. H

|timeptr üyesi|Değer|
|--------------------|-----------|
|**tm_hour**|Saatleri gece yarısından (0-23)|
|**tm_isdst**|Gün ışığından yararlanma etkinse pozitif; gün ışığından yararlanma etkin değilse, 0; Yaz Saati durum bilinmiyorsa, negatif. C çalışma zamanı kitaplığı, gün ışığından yararlanma saatine (DST) hesaplanması uygulamak için ABD kurallarını varsayar.|
|**tm_mday**|Ayın günü (1-31)|
|**tm_min**|Saat (0-59) dakika|
|**tm_mon**|Ay (0-11; Ocak = 0)|
|**tm_sec**|(0-59) dakikadan sonra saniye|
|**tm_wday**|Haftanın günü (0-6; Pazar = 0)|
|**tm_yday**|(0-365; yılın günü 1 Ocak = 0)|
|**tm_year**|Yıl (mevcut yıl eksi 1900)|

Dönüştürülmüş karakteri dize ayrıca yerel saat dilimi ayarlarını göre ayarlanır. Bkz: [zaman, _time32 _time64](time-time32-time64.md), [_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md), ve [localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md) işlevlerini yapılandırma hakkında bilgi yerel saat ve [_tzset](tzset.md) genel değişkenler ve saat dilimi ortamı tanımlama hakkında bilgi için işlevi.

Tarafından üretilen dize sonucu **asctime_s** tam olarak 26 karakter içerir ve form `Wed Jan 02 02:03:55 1980\n\0`. 24 saatlik düzende kullanılır. Tüm alanlar, sabit bir genişliğe sahiptir. Yeni satır karakteri ve null karakteri, dizenin son iki konum kaplar. İkinci parametre olarak geçirilen değer en az bu kadar büyük olmalıdır. Bir hata kodu daha az ise **EINVAL**, döndürülür.

**_wasctime_s** geniş karakterli sürümüdür **asctime_s**. **_wasctime_s** ve **asctime_s** aynı şekilde davranır.

### <a name="generic-text-routine-mapping"></a>Genel metin yordam eşlemesi

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tasctime_s**|**asctime_s**|**asctime_s**|**_wasctime_s**|

C++ dilinde bu işlevlerin kullanılması şablon aşırı yüklemeleriyle basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğu bir boyut bağımsız değişkeni belirtme gereksinimi ortadan otomatik olarak çıkarabilir. Daha fazla bilgi için [güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**asctime_s**|\<TIME.h >|
|**_wasctime_s**|\<TIME.h > veya \<wchar.h >|

## <a name="security"></a>Güvenlik

Arabelleğin işaretçisini değilse **NULL** ve geçerli bir arabellek için İşaretçi işaret etmiyor, işlev konumunda ne olursa olsun üzerine yazar. Bu, ayrıca bir erişim ihlali ile sonuçlanabilir.

A [arabellek taşması](/windows/desktop/SecBP/avoiding-buffer-overruns) geçirilen bağımsız değişkenin boyutu arabelleğinin gerçek boyutundan büyükse oluşabilir.

## <a name="example"></a>Örnek

Bu program, sistem saatini uzun tamsayı olarak yerleştirir **aclock**, yapısına çevirir **newtime** ve ardından için dize biçiminde çıktı, kullanarak **asctime_s**işlevi.

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
