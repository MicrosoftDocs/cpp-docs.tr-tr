---
title: _utime, _utime32, _utime64, _wutime, _wutime32, _wutime64
ms.date: 4/2/2020
api_name:
- _utime64
- _utime
- _wutime
- _wutime64
- _wutime32
- _utime32
- _o__utime32
- _o__utime64
- _o__wutime32
- _o__wutime64
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
- _tutime
- _utime64
- wutime
- utime32
- wutime64
- _utime
- wutime32
- _wutime
- utime
- utime64
- _wutime64
- _utime32
- _tutime64
- _wutime32
helpviewer_keywords:
- tutime function
- utime32 function
- utime64 function
- _utime function
- _tutime32 function
- time [C++], file modification
- wutime function
- _wutime function
- _wutime32 function
- _tutime64 function
- _tutime function
- files [C++], modification time
- _wutime64 function
- _utime32 function
- utime function
- _utime64 function
- wutime64 function
- wutime32 function
- tutime64 function
- tutime32 function
ms.assetid: 8d482d40-19b9-4591-bfee-5d7f601d1a9e
ms.openlocfilehash: 5c530f46877bdb23fc51fb49beab8abfc0c16b2f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81361201"
---
# <a name="_utime-_utime32-_utime64-_wutime-_wutime32-_wutime64"></a>_utime, _utime32, _utime64, _wutime, _wutime32, _wutime64

Dosya değiştirme süresini ayarlayın.

## <a name="syntax"></a>Sözdizimi

```C
int _utime(
   const char *filename,
   struct _utimbuf *times
);
int _utime32(
   const char *filename,
   struct __utimbuf32 *times
);
int _utime64(
   const char *filename,
   struct __utimbuf64 *times
);
int _wutime(
   const wchar_t *filename,
   struct _utimbuf *times
);
int _wutime32(
   const wchar_t *filename,
   struct __utimbuf32 *times
);
int _wutime64(
   const wchar_t *filename,
   struct __utimbuf64 *times
);
```

### <a name="parameters"></a>Parametreler

*filename*<br/>
Yol veya dosya adı içeren bir dize işaretçisi.

*Kez*<br/>
Zaman değerlerini depolanan işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Dosya değiştirme süresi değiştirildiyse, bu işlevlerin her biri 0 döndürür. -1'in geri dönüş değeri bir hatayı gösterir. Geçersiz bir parametre geçirilirse, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin verilirse, bu işlevler -1 döndürür ve **errno** aşağıdaki değerlerden birine ayarlanır:

|errno değeri|Koşul|
|-|-|
| **EACCES** | Yol dizini veya salt okunur dosyasını belirtir |
| **Eınval** | Geçersiz *saatler* bağımsız değişkeni |
| **EMFILE** | Çok fazla açık dosya (dosya değişiklik süresini değiştirmek için açılmalıdır) |
| **Enoent** | Yol veya dosya adı bulunamadı |

Bunlar ve diğer iade kodları hakkında daha fazla bilgi için [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bakın.

Değişiklik tarihi gece yarısından sonra, 1 Ocak 1970'te ve kullanılan işlevin bitiş tarihinden önceyse, bir dosya için tarih değiştirilebilir. **_utime** ve **_wutime** 64 bitlik bir zaman değeri kullanır, bu nedenle bitiş tarihi 23:59:59, 31 Aralık 3000 UTC'dir. **_USE_32BIT_TIME_T** eski davranışı zorlamak için tanımlanmışsa, bitiş tarihi 23:59:59 18 Ocak 2038, UTC'dir. **_utime32** veya **_wutime32,** **_USE_32BIT_TIME_T** tanımlanıp tanımlanmadığına bakılmaksızın 32 bitlik bir zaman türü kullanın ve her zaman önceki bitiş tarihine sahip olun. **_utime64** veya **_wutime64** her zaman 64 bit zaman türünü kullanır, bu nedenle bu işlevler her zaman sonraki bitiş tarihini destekler.

## <a name="remarks"></a>Açıklamalar

**_utime** işlevi *dosya adı*ile belirtilen dosyanın değişiklik saatini ayarlar. İşlem, zamanı değiştirmek için dosyaya yazma erişimine sahip olmalıdır. Windows işletim sisteminde, **_utimbuf** yapısındaki erişim süresini ve değişiklik süresini değiştirebilirsiniz. *Zaman* bir **NULL** işaretçisiyse, değişiklik zamanı geçerli yerel saate ayarlanır. Aksi takdirde, *kez* SYS\UTIME tanımlanan tip **_utimbuf**bir yapıya işaret etmelidir. H.

**_utimbuf** yapısı, dosya değişiklik tarihlerini değiştirmek için **_utime** tarafından kullanılan dosya erişim ve değişiklik saatlerini depolar. Yapı, her ikisi de tip **time_t**aşağıdaki alanlara sahiptir:

| Alan |   |
|-------|---|
| **actime** | Dosya erişim zamanı |
| **modtime** | Dosya değiştirme zamanı |

**_utimbuf** yapısının **(_utimebuf32** ve **__utimbuf64)** belirli sürümleri, zaman türünün 32 bit ve 64 bit sürümleri kullanılarak tanımlanır. Bunlar, bu işlevin 32 bit ve 64 bit belirli sürümlerinde kullanılır. **_utimbuf** kendisi varsayılan olarak **_USE_32BIT_TIME_T** tanımlanmadıkça 64 bitlik bir zaman türü kullanır.

**_utime,** **_utime** *dosya adı* bağımsız değişkeninin, açık bir dosyanın dosya tanımlayıcısı yerine bir dosya adı veya dosyaya giden yol olması dışında **_futime** ile aynıdır.

**_wutime** **_utime**geniş karakterli bir versiyonudur; **_wutime** için *dosya adı* bağımsız değişkeni geniş karakterli bir dizedir. Bu işlevler aynı şekilde başka türlü çalışır.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tutime**|**_utime**|**_utime**|**_wutime**|
|**_tutime32**|**_utime32**|**_utime32**|**_wutime32**|
|**_tutime64**|**_utime64**|**_utime64**|**_wutime64**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli üstbilgi|İsteğe bağlı üstbilgi|
|-------------|----------------------|----------------------|
|**_utime**, **_utime32**, **_utime64**|\<sys/utime.h>|\<errno.h>|
|**_utime64**|\<sys/utime.h>|\<errno.h>|
|**_wutime**|\<utime.h> \<veya wchar.h>|\<errno.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

Bu program, dosya değiştirme süresini geçerli saate ayarlamak için **_utime** kullanır.

```C
// crt_utime.c
#include <stdio.h>
#include <stdlib.h>
#include <sys/types.h>
#include <sys/utime.h>
#include <time.h>

int main( void )
{
   struct tm tma = {0}, tmm = {0};
   struct _utimbuf ut;

   // Fill out the accessed time structure
   tma.tm_hour = 12;
   tma.tm_isdst = 0;
   tma.tm_mday = 15;
   tma.tm_min = 0;
   tma.tm_mon = 0;
   tma.tm_sec = 0;
   tma.tm_year = 103;

   // Fill out the modified time structure
   tmm.tm_hour = 12;
   tmm.tm_isdst = 0;
   tmm.tm_mday = 15;
   tmm.tm_min = 0;
   tmm.tm_mon = 0;
   tmm.tm_sec = 0;
   tmm.tm_year = 102;

   // Convert tm to time_t
   ut.actime = mktime(&tma);
   ut.modtime = mktime(&tmm);

   // Show file time before and after
   system( "dir crt_utime.c" );
   if( _utime( "crt_utime.c", &ut ) == -1 )
      perror( "_utime failed\n" );
   else
      printf( "File time modified\n" );
   system( "dir crt_utime.c" );
}
```

### <a name="sample-output"></a>Örnek Çıktı

```Output
Volume in drive C has no label.
Volume Serial Number is 9CAC-DE74

Directory of C:\test

01/09/2003  05:38 PM               935 crt_utime.c
               1 File(s)            935 bytes
               0 Dir(s)  20,742,955,008 bytes free
File time modified
Volume in drive C has no label.
Volume Serial Number is 9CAC-DE74

Directory of C:\test

01/15/2002  12:00 PM               935 crt_utime.c
               1 File(s)            935 bytes
               0 Dir(s)  20,742,955,008 bytes free
```

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Yönetimi](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[_futime, _futime32, _futime64](futime-futime32-futime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[_stat, _wstat Fonksiyonlar](stat-functions.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
