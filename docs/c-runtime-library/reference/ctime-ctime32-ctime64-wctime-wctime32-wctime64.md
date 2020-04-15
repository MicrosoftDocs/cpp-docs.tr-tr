---
title: ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64
ms.date: 4/2/2020
api_name:
- _ctime64
- _wctime32
- ctime
- _wctime64
- _ctime32
- _wctime
- _o__wctime32
- _o__wctime64
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
- _wctime64
- _ctime32
- _tctime
- _wctime
- _wctime32
- _tctime64
- _ctime64
- ctime
helpviewer_keywords:
- tctime64 function
- _ctime32 function
- ctime32 function
- _wctime function
- wctime64 function
- _tctime64 function
- _tctime32 function
- _ctime64 function
- _wctime64 function
- ctime function
- wctime32 function
- ctime64 function
- _wctime32 function
- _tctime function
- tctime32 function
- tctime function
- wctime function
- time, converting
ms.assetid: 2423de37-a35c-4f0a-a378-3116bc120a9d
ms.openlocfilehash: 6056ad8bac6561c0ce2902928364996b2be9ae92
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348243"
---
# <a name="ctime-_ctime32-_ctime64-_wctime-_wctime32-_wctime64"></a>ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64

Bir saat değerini dize dönüştürün ve yerel saat dilimi ayarları için ayarlayın. Bu işlevlerin daha güvenli sürümleri mevcuttur; [ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
char *ctime( const time_t *sourceTime );
char *_ctime32( const __time32_t *sourceTime );
char *_ctime64( const __time64_t *sourceTime );
wchar_t *_wctime( const time_t *sourceTime );
wchar_t *_wctime32( const __time32_t *sourceTime );
wchar_t *_wctime64( const __time64_t *sourceTime );
```

### <a name="parameters"></a>Parametreler

*kaynakZaman*<br/>
Dönüştürme zamanı nın depolanmış olması için işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Karakter dizesi sonucu için bir işaretçi. **Null** döndürülür:

- *sourceTime* gece yarısından önceki bir tarihi temsil eder, 1 Ocak 1970, UTC.

- **_ctime32** veya **_wctime32** kullanıyorsanız ve *sourceTime* 23:59:59 18 Ocak 2038, UTC'den sonraki bir tarihi temsil eder.

- **_ctime64** veya **_wctime64** kullanıyorsanız ve *sourceTime* 23:59:59, 31 Aralık 3000, UTC'den sonraki bir tarihi temsil eder.

**ctime** **_ctime64** değerlendiren bir satır dışı fonksiyondur ve **time_t** **__time64_t**eşdeğerdir. Derleyiciyi **time_t** eski 32 bit **time_t**olarak yorumlamaya zorlamanız gerekiyorsa, **_USE_32BIT_TIME_T**tanımlayabilirsiniz. Bunu yapmak **ctime** **_ctime32**değerlendirmek için neden olur. Başvurunuz 18 Ocak 2038'den sonra başarısız olabileceğinden ve 64 bit platformlarda izin verilmediği için bu önerilmez.

## <a name="remarks"></a>Açıklamalar

**Ctime** işlevi, [time_t](../../c-runtime-library/standard-types.md) değeri olarak depolanan bir zaman değerini bir karakter dizesine dönüştürür. *SourceTime* değeri genellikle gece yarısından [time](time-time32-time64.md)(00:00:00), 1 Ocak 1970, eşgüdümlü evrensel saat (UTC) bu yana geçen saniye sayısını döndüren zaman aramadan elde edilir. İade değeri dizesi tam olarak 26 karakter içerir ve forma sahiptir:

```Output
Wed Jan 02 02:03:55 1980\n\0
```

24 saatlik bir saat kullanılır. Tüm alanların sabit bir genişliği vardır. Yeni satır karakteri ('\n') ve null karakter ('\0') dizesinin son iki pozisyonlarını kaplar.

Dönüştürülen karakter dizesi de yerel saat dilimi ayarlarına göre ayarlanır. Yerel saati ve [_tzset](tzset.md) işlevini yapılandırma hakkında bilgi için [saat,](time-time32-time64.md) [_ftime](ftime-ftime32-ftime64.md)ve [yerel saat](localtime-localtime32-localtime64.md) işlevlerini görün, saat dilimi ortamını ve genel değişkenleri tanımlama yla ilgili ayrıntılar için.

**Ctime** için bir çağrı **gmtime** ve **yerel saat** işlevleri tarafından kullanılan tek statik ayrılmış arabellek değiştirir. Bu yordamlardan birine yapılan her arama, önceki aramanın sonucunu yok eder. **ctime,** **asctime** işlevi ile statik bir arabelleği paylaşır. Böylece, **ctime** bir çağrı **asctime, localtime**veya **localtime** **gmtime**için önceki arama sonuçlarını yok eder.

**_wctime** ve **_wctime64** **ctime** ve **_ctime64**geniş karakterli versiyonu; geniş karakter dizesine bir işaretçi döndürme. Aksi takdirde, **_ctime64**, **_wctime**, ve **_wctime64** **ctime**aynı şekilde davranan .

Bu işlevler parametrelerini doğrular. *SourceTime* null işaretçisi ise veya *kaynakZaman* değeri negatifse, bu işlevler [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmedevam etmesine izin verilirse, işlevler **NULL** döndürdü ve **EINVAL** **için errno** ayarlayın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tctime**|**Ctime**|**Ctime**|**_wctime**|
|**_tctime32**|**_ctime32**|**_ctime32**|**_wctime32**|
|**_tctime64**|**_ctime64**|**_ctime64**|**_wctime64**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**Ctime**|\<time.h>|
|**_ctime32**|\<time.h>|
|**_ctime64**|\<time.h>|
|**_wctime**|\<time.h> \<veya wchar.h>|
|**_wctime32**|\<time.h> \<veya wchar.h>|
|**_wctime64**|\<time.h> \<veya wchar.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

```C
// crt_ctime64.c
// compile with: /W3
/* This program gets the current
* time in _time64_t form, then uses ctime to
* display the time in string form.
*/

#include <time.h>
#include <stdio.h>

int main( void )
{
   __time64_t ltime;

   _time64( &ltime );
   printf( "The time is %s\n", _ctime64( &ltime ) ); // C4996
   // Note: _ctime64 is deprecated; consider using _ctime64_s
}
```

```Output
The time is Wed Feb 13 16:04:43 2002
```

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Yönetimi](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
