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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 7dc87f417db93f8ad0d90de1270c19997669fb7c
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82914832"
---
# <a name="ctime-_ctime32-_ctime64-_wctime-_wctime32-_wctime64"></a>ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64

Bir zaman değerini dizeye dönüştürün ve yerel saat dilimi ayarlarını yapın. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz. [ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md).

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
Dönüştürülecek saklı zamana yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Karakter dizesi sonucuna yönelik bir işaretçi. Şu durumlarda **null değeri** döndürülür:

- *Sourcetime* , 1 Ocak 1970, UTC 'nin gece yarısından önceki bir tarihi temsil eder.

- **_Ctime32** veya **_Wctime32** kullanırsanız ve *sourcetime* , 23:59:59 Ocak 2038, UTC 'den sonraki bir tarihi temsil eder.

- **_Ctime64** veya **_Wctime64** kullanırsanız ve *Sourcetime* 23:59:59, 31 Aralık 3000, UTC 'den sonraki bir tarihi temsil eder.

**CTime** , **_ctime64** değerlendirilen ve **time_t** **__time64_t**eşdeğer bir satır içi işlevdir. Derleyicinin **time_t** eski 32 bit **time_t**olarak yorumlamasını zorlamak istiyorsanız **_USE_32BIT_TIME_T**tanımlayabilirsiniz. Bunu yapmak, **CTime** 'ın **_ctime32**değerlendirmesini sağlar. Uygulamanız 18 Ocak 2038 ' den sonra başarısız olabileceğinden ve 64-bit platformlarda izin verilmediği için bu önerilmez.

## <a name="remarks"></a>Açıklamalar

**CTime** işlevi, bir [time_t](../../c-runtime-library/standard-types.md) değeri olarak depolanan bir zaman değerini bir karakter dizesine dönüştürür. *Sourcetime* değeri genellikle gece yarısından beri geçen saniye sayısı ( [time](time-time32-time64.md)00:00:00), 1 Ocak 1970, Eşgüdümlü Evrensel Saat (UTC) döndüren bir çağrıdan alınmıştır. Dönüş değeri dizesi tam 26 karakter içerir ve şu biçimdedir:

```Output
Wed Jan 02 02:03:55 1980\n\0
```

24 saatlik bir saat kullanılır. Tüm alanların sabit bir genişliği vardır. Yeni satır karakteri (' \n ') ve null karakteri (' \ 0 ') dizenin son iki konumunu kaplar.

Dönüştürülen karakter dizesi de yerel saat dilimi ayarlarına göre ayarlanır. Yerel saati yapılandırma hakkında bilgi için [saat](time-time32-time64.md), [_ftime](ftime-ftime32-ftime64.md)ve [localtime](localtime-localtime32-localtime64.md) işlevlerine ve saat dilimi ortamının ve genel değişkenlerin tanımlanması hakkındaki ayrıntılar için [_tzset](tzset.md) işlevine bakın.

**CTime** çağrısı, **gmtime** ve **localtime** işlevleri tarafından kullanılan tek statik olarak ayrılan arabelleği değiştirir. Bu yordamların birine yapılan her bir çağrı, önceki çağrının sonucunu yok eder. **CTime** , **asctime** işleviyle bir statik arabelleği paylaşır. Bu nedenle, bir **CTime** çağrısı, önceki tüm çağrı sonuçlarını **asctime**, **localtime**veya **gmtime**öğesine yok eder.

**_wctime** ve **_wctime64** , **CTime** ve **_ctime64**'nin geniş karakterli sürümüdür; geniş karakterli dizeye bir işaretçi döndürülüyor. Aksi takdirde, **_ctime64**, **_wctime**ve **_wctime64** **CTime**ile aynı şekilde davranır.

Bu işlevler, parametrelerini doğrular. *Sourcetime* null bir işaretçisiyse veya *sourcetime* değeri negatifse, bu işlevler [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, işlevler **null** döndürür ve **errno** , **EINVAL**olarak ayarlanır.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tctime**|**CTime**|**CTime**|**_wctime**|
|**_tctime32**|**_ctime32**|**_ctime32**|**_wctime32**|
|**_tctime64**|**_ctime64**|**_ctime64**|**_wctime64**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**CTime**|\<Time. h>|
|**_ctime32**|\<Time. h>|
|**_ctime64**|\<Time. h>|
|**_wctime**|\<Time. h> veya \<wchar. h>|
|**_wctime32**|\<Time. h> veya \<wchar. h>|
|**_wctime64**|\<Time. h> veya \<wchar. h>|

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
