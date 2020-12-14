---
description: 'Hakkında daha fazla bilgi edinin: asctime_s _wasctime_s'
title: asctime_s, _wasctime_s
ms.date: 4/2/2020
api_name:
- _wasctime_s
- asctime_s
- _o__wasctime_s
- _o_asctime_s
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
ms.openlocfilehash: d743aea81abdba2e1aa2b470f71081cb92e6fc64
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97211329"
---
# <a name="asctime_s-_wasctime_s"></a>asctime_s, _wasctime_s

Bir **TM** zaman yapısını bir karakter dizesine Dönüştür. Bu işlevler, [CRT 'Daki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklanan şekilde, güvenlik geliştirmeleriyle [_wasctime asctime](asctime-wasctime.md) sürümleridir.

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
Karakter dizesi sonucunu depolamak için arabelleğin bir işaretçisi. Bu işlev, *numberOfElements* tarafından belirtilen boyuttaki geçerli bir bellek konumuna yönelik bir işaretçi olduğunu varsayar.

*numberOfElements*<br/>
Sonucu depolamak için kullanılan arabelleğin boyutu.

*tmSource*<br/>
Saat/tarih yapısı. Bu işlev, geçerli bir TM nesnesine bir işaretçi olduğunu varsayar **`struct`**  .

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır. Bir hata oluşursa, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, dönüş değeri bir hata kodudur. Hata kodları ERRNO. H içinde tanımlanır. Daha fazla bilgi için bkz. [errno sabitleri](../../c-runtime-library/errno-constants.md). Her bir hata koşulu için döndürülen gerçek hata kodları aşağıdaki tabloda gösterilmiştir.

### <a name="error-conditions"></a>Hata koşulları

|*arabelleğin*|*numberOfElements*|*tmSource*|Döndürülmesini|*Arabellekteki* değer|
|--------------|------------------------|----------|------------|-----------------------|
|**DEĞER**|Herhangi biri|Herhangi biri|**EıNVAL**|Değiştirilmedi|
|**Null** değil (geçerli belleğe işaret eder)|0|Herhangi bir|**EıNVAL**|Değiştirilmedi|
|**Null** değil|0< boyutu < 26|Herhangi bir|**EıNVAL**|Boş dize|
|**Null** değil|>= 26|**DEĞER**|**EıNVAL**|Boş dize|
|**Null** değil|>= 26|Zaman bileşenleri için geçersiz zaman yapısı veya Aralık değerleri|**EıNVAL**|Boş dize|

> [!NOTE]
> **Wasctime_s** için hata koşulları, boyut sınırının sözcüklerle ölçüldüğü özel durumla **asctime_s** benzerdir.

## <a name="remarks"></a>Açıklamalar

**Asctime** işlevi bir yapı olarak depolanan bir saati bir karakter dizesine dönüştürür. *Tmsource* değeri genellikle **gmtime** veya **localtime** çağrısından alınır. Her iki işlev de, TIME. H içinde tanımlandığı şekilde bir **TM** yapısını doldurmanız için kullanılabilir.

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

Dönüştürülen karakter dizesi de yerel saat dilimi ayarlarına göre ayarlanır. Saat dilimi ortamı ve genel değişkenleri tanımlama hakkında bilgi için yerel saati ve [_ftime64](tzset.md) işlevini yapılandırma hakkında bilgi için [zaman, _time32, _time64](time-time32-time64.md), [_ftime, _ftime32, localtime_s](ftime-ftime32-ftime64.md)ve _localtime32_s [,](localtime-s-localtime32-s-localtime64-s.md) _localtime64_s, _tzset işlevlerine bakın.

**Asctime_s** tarafından üretilen dize sonucu, tam 26 karakter içerir ve forma sahiptir `Wed Jan 02 02:03:55 1980\n\0` . 24 saatlik bir saat kullanılır. Tüm alanların sabit bir genişliği vardır. Yeni satır karakteri ve null karakter, dizenin son iki konumunu kaplar. İkinci parametre olarak geçirilen değer en az bu büyük olmalıdır. Daha az ise, **EINVAL** bir hata kodu döndürülür.

**_wasctime_s** , **asctime_s** geniş karakterli bir sürümüdür. **_wasctime_s** ve **asctime_s** aynı şekilde davranır.

Bu işlevlerin hata ayıklama Kitaplığı sürümleri ilk olarak arabelleği 0xFE ile doldurur. Bu davranışı devre dışı bırakmak için [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md)kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mapping"></a>Generic-Text rutin eşleme

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tasctime_s**|**asctime_s**|**asctime_s**|**_wasctime_s**|

C++ ' da, bu işlevlerin kullanılması şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkarabilir ve bir boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırır. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**asctime_s**|\<time.h>|
|**_wasctime_s**|\<time.h> veya \<wchar.h>|

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
