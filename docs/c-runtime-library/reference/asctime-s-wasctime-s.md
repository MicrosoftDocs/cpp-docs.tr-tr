---
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 52391eb1237e4c1d7ef320dacd211b603a21ab8b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81334221"
---
# <a name="asctime_s-_wasctime_s"></a>asctime_s, _wasctime_s

**TM** zaman yapısını karakter dizesine dönüştürün. Bu işlevler, CRT'deki Güvenlik Özellikleri'nde açıklandığı gibi güvenlik geliştirmeleriyle [_wasctime asctime](asctime-wasctime.md) [sürümleridir.](../../c-runtime-library/security-features-in-the-crt.md)

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
Karakter dizesi sonucunu depolamak için arabellek için bir işaretçi. Bu *işlev, numberOfElements*tarafından belirtilen bir boyutu ile geçerli bir bellek konumu için bir işaretçi varsayar.

*numberOfElements*<br/>
Sonucu depolamak için kullanılan arabelleğe boyutu.

*tmKaynak*<br/>
Saat/tarih yapısı. Bu işlev, geçerli bir **struct** **tm** nesnesi için bir işaretçi varsayar.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır. Bir hata varsa, geçersiz parametre işleyicisi, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmenin devam etmesine izin verilirse, iade değeri bir hata kodudur. Hata kodları ERRNO'da tanımlanır. H. Daha fazla bilgi için [errno Constants'](../../c-runtime-library/errno-constants.md)a bakın. Her hata koşulu için döndürülen gerçek hata kodları aşağıdaki tabloda gösterilmiştir.

### <a name="error-conditions"></a>Hata Koşulları

|*Arabellek*|*numberOfElements*|*tmKaynak*|Dönüş|*Arabellekteki* değer|
|--------------|------------------------|----------|------------|-----------------------|
|**Null**|Herhangi biri|Herhangi biri|**Eınval**|Değiştirilmedi|
|**NULL** değil (geçerli belleğe işaret)|0|Herhangi biri|**Eınval**|Değiştirilmedi|
|**NULL** değil|0< boyutu < 26|Herhangi biri|**Eınval**|Boş dize|
|**NULL** değil|>= 26|**Null**|**Eınval**|Boş dize|
|**NULL** değil|>= 26|Geçersiz zaman yapısı veya zamanın bileşenleri için aralık dışı değerler|**Eınval**|Boş dize|

> [!NOTE]
> **wasctime_s** için hata koşulları, boyut sınırının sözcüklerle ölçülmesi dışında **asctime_s** benzer.

## <a name="remarks"></a>Açıklamalar

**Asctime** işlevi, yapı olarak depolanan bir zamanı karakter dizesine dönüştürür. *TmSource* değeri genellikle **gmtime** veya yerel **saat**için bir çağrı elde edilir. Her iki işlev de TIME'da tanımlandığı gibi bir **tm** yapısını doldurmak için kullanılabilir. H.

|timeptr üyesi|Değer|
|--------------------|-----------|
|**tm_hour**|Gece yarısından itibaren saatler (0-23)|
|**tm_isdst**|Yaz saati uygulaması geçerliyse pozitif; Yaz saati uygulaması geçerli değilse 0; gün ışığından yararlanma saatinin durumu bilinmiyorsa negatif. C çalışma zamanı kitaplığı, Gün Işığından Yararlanma Saati (DST) hesaplamasını uygulamak için ABD'nin kurallarını varsayar.|
|**tm_mday**|Ayın günü (1-31)|
|**tm_min**|Dakika sonra saat (0-59)|
|**tm_mon**|Ay (0-11; Ocak = 0)|
|**tm_sec**|Saniye dakika sonra (0-59)|
|**tm_wday**|Haftanın günü (0-6; Pazar = 0)|
|**tm_yday**|Yılın günü (0-365; 1 Ocak = 0)|
|**tm_year**|Yıl (şu anki yıl eksi 1900)|

Dönüştürülen karakter dizesi de yerel saat dilimi ayarlarına göre ayarlanır. Saat dilimi ortamını ve genel değişkenleri tanımlama hakkında bilgi almak için yerel saati ve [_tzset](tzset.md) işlevini yapılandırma hakkında bilgi için [saati, _time32, _time64,](time-time32-time64.md) [_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)ve [localtime_s, _localtime32_s](localtime-s-localtime32-s-localtime64-s.md) _localtime64_s işlevlerigörün.

**asctime_s** tarafından üretilen dize sonucu tam olarak 26 karakter içerir ve formu `Wed Jan 02 02:03:55 1980\n\0`vardır. 24 saatlik bir saat kullanılır. Tüm alanların sabit bir genişliği vardır. Yeni satır karakteri ve null karakter dize son iki pozisyonları işgal. İkinci parametre olarak geçirilen değer en azından bu kadar büyük olmalıdır. Daha az ise, bir hata kodu, **EINVAL**, döndürülür.

**_wasctime_s** **asctime_s**geniş karakterli bir sürümüdür. **_wasctime_s** ve **asctime_s** aynı şekilde aynı şekilde davranan.

Bu işlevlerin hata ayıklama kitaplığı sürümleri önce arabelleği 0xFE ile doldurur. Bu davranışı devre dışı kullanabilirsiniz, [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md)kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mapping"></a>Genel Metin Rutin Eşleme

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tasctime_s**|**asctime_s**|**asctime_s**|**_wasctime_s**|

C++'da, bu işlevleri kullanmak şablon aşırı yükleri ile basitleştirilir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkararak boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırabilir. Daha fazla bilgi için Bkz. [Güvenli Şablon Overloads.](../../c-runtime-library/secure-template-overloads.md)

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**asctime_s**|\<time.h>|
|**_wasctime_s**|\<time.h> \<veya wchar.h>|

## <a name="security"></a>Güvenlik

Arabellek işaretçisi **NULL** değilse ve işaretçi geçerli bir arabelleğe işaret etmiyorsa, işlev konumda ne varsa üzerine yazar. Bu da bir erişim ihlaline neden olabilir.

Geçirilen boyut bağımsız değişkeni arabelleğenin gerçek boyutundan büyükse, [arabellek taşma](/windows/win32/SecBP/avoiding-buffer-overruns) oluşabilir.

## <a name="example"></a>Örnek

Bu program uzun tamsayı **aclock**sistem zaman yerleştirir , yapı **ya da yeni zaman** çevirir ve daha sonra çıkış için dize formuna dönüştürür, **asctime_s** işlevini kullanarak.

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
