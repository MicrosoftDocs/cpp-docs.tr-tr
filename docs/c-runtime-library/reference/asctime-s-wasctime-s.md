---
title: asctime_s, _wasctime_s
ms.date: 11/04/2016
api_name:
- _wasctime_s
- asctime_s
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
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 0a40dad34d607bb52b062fc2cec163dfc8b62219
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70943668"
---
# <a name="asctime_s-_wasctime_s"></a>asctime_s, _wasctime_s

Bir **TM** zaman yapısını bir karakter dizesine Dönüştür. Bu işlevler, [CRT 'Daki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklanan şekilde, güvenlik geliştirmeleriyle [asctime, _wasctime](asctime-wasctime.md) sürümleridir.

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

*arabelleğin*<br/>
Karakter dizesi sonucunu depolamak için arabelleğin bir işaretçisi. Bu işlev, *numberOfElements*tarafından belirtilen boyuttaki geçerli bir bellek konumuna yönelik bir işaretçi olduğunu varsayar.

*numberOfElements*<br/>
Sonucu depolamak için kullanılan arabelleğin boyutu.

*tmSource*<br/>
Saat/tarih yapısı. Bu işlev, geçerli bir **struct** **TM** nesnesine yönelik bir işaretçi olduğunu varsayar.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır. Bir hata oluşursa, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, dönüş değeri bir hata kodudur. Hata kodları ERRNO içinde tanımlanmıştır. Olsun. Daha fazla bilgi için bkz. [errno sabitleri](../../c-runtime-library/errno-constants.md). Her bir hata koşulu için döndürülen gerçek hata kodları aşağıdaki tabloda gösterilmiştir.

### <a name="error-conditions"></a>Hata koşulları

|*arabelleğin*|*numberOfElements*|*tmSource*|döndürülmesini|*Arabellekteki* değer|
|--------------|------------------------|----------|------------|-----------------------|
|**DEĞER**|Any|Any|**EINVAL**|değiştirilmedi|
|**Null** değil (geçerli belleğe işaret eder)|0|Any|**EINVAL**|değiştirilmedi|
|**Null** değil|0 < boyutu < 26|Any|**EINVAL**|Boş dize|
|**Null** değil|>= 26|**DEĞER**|**EINVAL**|Boş dize|
|**Null** değil|>= 26|Zaman bileşenleri için geçersiz zaman yapısı veya Aralık değerleri|**EINVAL**|Boş dize|

> [!NOTE]
> **Wasctime_s** için hata koşulları, boyut sınırının sözcüklerle ölçüldüğü özel durum **asctime_s** ile benzerdir.

## <a name="remarks"></a>Açıklamalar

**Asctime** işlevi bir yapı olarak depolanan bir saati bir karakter dizesine dönüştürür. *Tmsource* değeri genellikle **gmtime** veya **localtime**çağrısından alınır. Her iki işlev de bir **TM** yapısını, zaman içinde tanımlandığı şekilde doldurmanız için kullanılabilir. Olsun.

|timeptr üyesi|Değer|
|--------------------|-----------|
|**tm_hour**|Gece yarısından itibaren saat (0-23)|
|**tm_isdst**|Günışığından yararlanma süresi etkinse pozitif; gün ışığından yararlanma saati etkin değilse 0; gün ışığından yararlanma zamanının durumu bilinmiyorsa negatif olur. C çalışma zamanı kitaplığı, gün ışığından yararlanma zamanının (DST) hesaplanmasını uygulamak için Birleşik Devletler ' kurallarını varsayar.|
|**tm_mday**|Ayın günü (1-31)|
|**tm_min**|Saat sonra dakika (0-59)|
|**tm_mon**|Ay (0-11; Ocak = 0)|
|**tm_sec**|Dakika sonra saniye (0-59)|
|**tm_wday**|Haftanın günü (0-6; Pazar = 0)|
|**tm_yday**|Yılın günü (0-365; 1 Ocak = 0)|
|**tm_year**|Yıl (geçerli yıl eksi 1900)|

Dönüştürülen karakter dizesi de yerel saat dilimi ayarlarına göre ayarlanır. Yerel saati ve [_tzset](tzset.md) işlevini yapılandırma hakkında bilgi için bkz. [_time32, _time64](time-time32-time64.md), [_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)ve [localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md) Functions Saat dilimi ortamını ve genel değişkenleri tanımlama.

**Asctime_s** tarafından üretilen dize sonucu tam 26 karakter içerir ve forma `Wed Jan 02 02:03:55 1980\n\0`sahiptir. 24 saatlik bir saat kullanılır. Tüm alanların sabit bir genişliği vardır. Yeni satır karakteri ve null karakter, dizenin son iki konumunu kaplar. İkinci parametre olarak geçirilen değer en az bu büyük olmalıdır. Daha az ise, **EINVAL**bir hata kodu döndürülür.

**_wasctime_s** , **asctime_s**öğesinin geniş karakterli bir sürümüdür. **_wasctime_s** ve **asctime_s** aynı şekilde davranır.

### <a name="generic-text-routine-mapping"></a>Genel metin rutin eşleme

|TCHAR.H yordamı|_UNıCODE & _MBCS tanımlı değil|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tasctime_s**|**asctime_s**|**asctime_s**|**_wasctime_s**|

' C++De, bu işlevlerin kullanılması şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkarabilir ve bir boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırır. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**asctime_s**|\<Time. h >|
|**_wasctime_s**|\<Time. h > veya \<wchar. h >|

## <a name="security"></a>Güvenlik

Arabellek işaretçisi **null** değilse ve işaretçi geçerli bir arabelleği işaret etmez, işlev konumdaki her şeyi üzerine yazar. Bu da erişim ihlaline yol açabilir.

Geçirilen boyut bağımsız değişkeni arabelleğin gerçek boyutundan fazlaysa bir [arabellek taşması](/windows/win32/SecBP/avoiding-buffer-overruns) meydana gelebilir.

## <a name="example"></a>Örnek

Bu program, sistem saatini uzun tamsayı **ACLOCK**'a koyar, onu **Newtime** yapısına çevirir ve sonra **asctime_s** işlevini kullanarak çıktı için dize biçimine dönüştürür.

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
