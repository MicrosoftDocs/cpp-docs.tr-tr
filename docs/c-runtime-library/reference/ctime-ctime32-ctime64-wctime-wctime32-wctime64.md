---
title: ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64
ms.date: 11/04/2016
apiname:
- _ctime64
- _wctime32
- ctime
- _wctime64
- _ctime32
- _wctime
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
ms.openlocfilehash: d1858a36c68a2ca5cedf70a1d74d5f250cbac8df
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62288609"
---
# <a name="ctime-ctime32-ctime64-wctime-wctime32-wctime64"></a>ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64

Bir zaman değeri dizeye Dönüştür ve yerel saat dilimi ayarlarını yapın. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz: [ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md).

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

*sourceTime*<br/>
Dönüştürülecek depolanan zamana yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Karakter dize sonucu için bir işaretçi. **NULL** olursa döndürülür:

- *sourceTime* 1 Ocak 1970 gece yarısı UTC tarihi temsil eder.

- Kullanırsanız **_ctime32** veya **_wctime32** ve *sourceTime* 23:59:59 18 Ocak 2038, UTC tarihinden temsil eder.

- Kullanırsanız **_ctime64** veya **_wctime64** ve *sourceTime* 23:59:59, 31 Aralık, 3000, UTC tarihinden temsil eder.

**CTime** olarak değerlendirilen bir satır içi işlev **_ctime64** ve **time_t** eşdeğerdir **__time64_t**. Yorumlamak üzere zorlamanız gerekirse **time_t** eski 32-bit olarak **time_t**, tanımlayabileceğiniz **_use_32bıt_tıme_t**. Bunun yapılması neden olacak **ctime** için değerlendirilecek **_ctime32**. Bu, 18 Ocak 2038 sonrasında uygulamanız çalışmayabilir ve 64-bit platformlarda izin verilmiyor çünkü önerilmez.

## <a name="remarks"></a>Açıklamalar

**Ctime** işlevi olarak depolanan bir saat değerine dönüştürür bir [time_t](../../c-runtime-library/standard-types.md) bir karakter dizesi değeri. *SourceTime* değeri çağrısından alınan genellikle [zaman](time-time32-time64.md), saniye cinsinden gece yarısından beri geçen döndüren (00: 00:00), 1 Ocak 1970, Eşgüdümlü Evrensel Saat (UTC). Dönüş değeri dize, tam olarak 26 karakterler içeriyor ve biçime sahiptir:

```Output
Wed Jan 02 02:03:55 1980\n\0
```

24 saatlik düzende kullanılır. Tüm alanlar, sabit bir genişliğe sahiptir. Yeni satır karakteri ('\n') ve null karakteri ('\0'), son iki dize konumlarını kaplar.

Dönüştürülmüş karakteri dize ayrıca yerel saat dilimi ayarlarını göre ayarlanır. Bkz [zaman](time-time32-time64.md), [_ftime](ftime-ftime32-ftime64.md), ve [localtime](localtime-localtime32-localtime64.md) yerel saat yapılandırma hakkında bilgi için İşlevler ve [_tzset](tzset.md) için işlevi Genel değişkenler ve saat dilimi ortamı tanımlama hakkında ayrıntılar.

Bir çağrı **ctime** tarafından kullanılan tek bir statik olarak ayrılan arabelleğe değiştirir **gmtime** ve **localtime** işlevleri. Bu yordamların her çağrısına, önceki çağrının sonucu yok eder. **CTime** statik bir arabellek ile paylaşır **asctime** işlevi. Bu nedenle, bir çağrı **ctime** için tüm önceki çağrının sonuçlarını yok eder **asctime**, **localtime**, veya **gmtime**.

**_wctime** ve **_wctime64** geniş karakter sürümüne sahip **ctime** ve **_ctime64**; geniş karakter dizesine bir işaretçi döndürüyor. Aksi takdirde, **_ctime64**, **_wctime**, ve **_wctime64** öğesine aynı şekilde davranır **ctime**.

Bu işlevler kendi parametrelerini doğrular. Varsa *sourceTime* null bir işaretçiyse veya *sourceTime* değeri negatif ise, bu işlevler içinde açıklanan şekilde geçersiz parametre işleyicisi çağırır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, İşlevler döndürür **NULL** ayarlayıp **errno** için **EINVAL**.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tctime**|**CTime**|**CTime**|**_wctime**|
|**_tctime32**|**_ctime32**|**_ctime32**|**_wctime32**|
|**_tctime64**|**_ctime64**|**_ctime64**|**_wctime64**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**CTime**|\<TIME.h >|
|**_ctime32**|\<TIME.h >|
|**_ctime64**|\<TIME.h >|
|**_wctime**|\<TIME.h > veya \<wchar.h >|
|**_wctime32**|\<TIME.h > veya \<wchar.h >|
|**_wctime64**|\<TIME.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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
