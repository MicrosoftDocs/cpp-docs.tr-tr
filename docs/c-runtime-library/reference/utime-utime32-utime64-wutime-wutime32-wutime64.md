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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: dbff557cd116eb1df44f015b17716408c8dc54c2
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82912124"
---
# <a name="_utime-_utime32-_utime64-_wutime-_wutime32-_wutime64"></a>_utime, _utime32, _utime64, _wutime, _wutime32, _wutime64

Dosya değiştirme saatini ayarlayın.

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
Yolu veya dosya adını içeren bir dize işaretçisi.

*sayısıdır*<br/>
Depolanan saat değerlerine yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri, dosya değiştirme saati değiştirilmişse 0 döndürür. -1 ' in dönüş değeri bir hatayı gösterir. Geçersiz bir parametre geçirilmemişse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler-1 döndürür ve **errno** aşağıdaki değerlerden birine ayarlanır:

|errno değeri|Koşul|
|-|-|
| **EACCES** | Yol, dizini veya salt okunurdur dosyayı belirtir |
| **EıNVAL** | Geçersiz *bağımsız* değişken |
| **EMFıLE** | Çok fazla açık dosya (dosyanın değiştirilme süresini değiştirmek için açılması gerekir) |
| **ENOENT** | Yol veya dosya adı bulunamadı |

Bu ve diğer dönüş kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) .

Değişiklik tarihi gece yarısından sonra, 1 Ocak 1970 ve kullanılan işlevin bitiş tarihinden önce olursa Tarih bir dosya için değiştirilebilir. **_utime** ve **_wutime** 64 bitlik bir zaman değeri kullanır, bu nedenle bitiş tarihi 23:59:59, 31 Aralık 3000, UTC olur. Eski davranışı zorlamak için **_USE_32BIT_TIME_T** tanımlanmışsa, bitiş tarihi 18 Ocak 2038, UTC olarak 23:59:59. **_utime32** veya **_wutime32** , **_USE_32BIT_TIME_T** tanımlanıp tanımlanmadığına bakılmaksızın 32 bitlik bir zaman türü kullanır ve her zaman eski bitiş tarihine sahip olur. **_utime64** veya **_wutime64** her zaman 64 bitlik saat türünü kullanır, bu nedenle bu işlevler her zaman sonraki bitiş tarihini destekler.

## <a name="remarks"></a>Açıklamalar

**_Utime** işlevi, *filename*tarafından belirtilen dosyanın değiştirilme saatini ayarlar. İşlemin saati değiştirmek için dosyaya yazma erişimi olmalıdır. Windows işletim sisteminde, **_utimbuf** yapısındaki erişim süresini ve değiştirme saatini değiştirebilirsiniz. *Süreler* **null** bir işaretçisiyse, değiştirme saati geçerli yerel saate ayarlanır. Aksi takdirde, *süreler* , sys\utimeiçinde tanımlanan **_utimbuf**türünde bir yapıya işaret etmelidir. Olsun.

**_Utimbuf** yapısı, dosya değiştirme tarihlerini değiştirmek için **_utime** tarafından kullanılan dosya erişimini ve değişiklik zamanlarını depolar. Yapının her ikisi de **time_t**aşağıdaki alanları vardır:

| Alan |   |
|-------|---|
| **actime** | Dosya erişiminin zamanı |
| **modsaat** | Dosya değişikliği zamanı |

**_Utimbuf** yapısının belirli sürümleri (**_utimebuf32** ve **__utimbuf64**), zaman türünün 32-bit ve 64 bit sürümleri kullanılarak tanımlanmıştır. Bunlar, bu işlevin 32-bit ve 64 bit özel sürümlerinde kullanılır. **_USE_32BIT_TIME_T** tanımlanmadığı müddetçe **_utimbuf** kendisini varsayılan olarak 64 bitlik bir zaman türü kullanır.

**_utime** , **_utime** dosya *adı* bağımsız değişkeninin bir dosya adı ya da bir dosyanın yolu olan dosya tanımlayıcısı yerine bir dosya adı olması dışında **_futime** aynıdır.

**_wutime** , **_utime**geniş karakterli bir sürümüdür; _wutime *dosya adı* bağımsız **_wutime** değişkeni, geniş karakterli bir dizedir. Bu işlevler, aynı şekilde davranır.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tutime**|**_utime**|**_utime**|**_wutime**|
|**_tutime32**|**_utime32**|**_utime32**|**_wutime32**|
|**_tutime64**|**_utime64**|**_utime64**|**_wutime64**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli üst bilgiler|İsteğe bağlı üstbilgiler|
|-------------|----------------------|----------------------|
|**_utime**, **_utime32**, **_utime64**|\<sys/utime. h>|\<errno. h>|
|**_utime64**|\<sys/utime. h>|\<errno. h>|
|**_wutime**|\<utime. h> veya \<wchar. h>|\<errno. h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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
[_stat, _wstat Işlevleri](stat-functions.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
