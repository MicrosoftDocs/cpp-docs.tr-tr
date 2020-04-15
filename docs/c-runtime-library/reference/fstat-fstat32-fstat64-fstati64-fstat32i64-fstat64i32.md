---
title: _fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32
ms.date: 4/2/2020
api_name:
- _fstat32
- _fstat64
- _fstati64
- _fstat
- _fstat64i32
- _fstat32i64
- _o__fstat32
- _o__fstat32i64
- _o__fstat64
- _o__fstat64i32
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
- api-ms-win-crt-filesystem-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _fstat32i64
- fstat
- fstat64i32
- _fstat64
- _fstati64
- fstat64
- _fstat32
- fstat32i64
- fstati64
- _fstat
- fstat32
- _fstat64i32
helpviewer_keywords:
- _fstat64 function
- fstati64 function
- _fstat64i32 function
- _fstat32i64 function
- _fstat32 function
- file information
- fstat64i32 function
- fstat32 function
- fstat function
- fstat64 function
- _fstat function
- _fstati64 function
- fstat32i64 function
ms.assetid: 088f5e7a-9636-4cf7-ab8e-e28d2aa4280a
ms.openlocfilehash: 02d297fec2ada545a8b693abacfecc7981149dae
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345666"
---
# <a name="_fstat-_fstat32-_fstat64-_fstati64-_fstat32i64-_fstat64i32"></a>_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32

Açık bir dosya hakkında bilgi alır.

## <a name="syntax"></a>Sözdizimi

```C
int _fstat(
   int fd,
   struct _stat *buffer
);
int _fstat32(
   int fd,
   struct __stat32 *buffer
);
int _fstat64(
   int fd,
   struct __stat64 *buffer
);
int _fstati64(
   int fd,
   struct _stati64 *buffer
);
int _fstat32i64(
   int fd,
   struct _stat32i64 *buffer
);
int _fstat64i32(
   int fd,
   struct _stat64i32 *buffer
);
```

### <a name="parameters"></a>Parametreler

*Fd*<br/>
Açık dosyanın dosya tanımlayıcısı.

*Arabellek*<br/>
Sonuçları depolamak için yapıyı işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Dosya durumu bilgileri elde edilirse 0 döndürür. -1'in geri dönüş değeri bir hatayı gösterir. Dosya tanımlayıcısı geçersizse veya *arabellek* **NULL**ise, Geçersiz parametre işleyicisi [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütme devam etmesine izin verilirse, **errno** **EBADF**ayarlanır , geçersiz bir dosya tanımlayıcı durumunda, ya da **EINVAL**için , *arabellek* **NULL**ise .

## <a name="remarks"></a>Açıklamalar

**_fstat** işlevi *fd* ile ilişkili açık dosya hakkında bilgi alır ve *arabellek*tarafından işaret edilen yapıda depolar. SYS\Stat.h'de tanımlanan **_stat** yapısı aşağıdaki alanları içerir.

|Alan|Anlamı|
|-|-|
| **st_atime** | Son dosya erişim zamanı. |
| **st_ctime** | Dosyanın oluşturulmama zamanı. |
| **st_dev** | Eğer bir cihaz, *fd*; aksi takdirde 0. |
| **st_mode** | Dosya modu bilgileri için bit maskesi. *fd* bir aygıta başvuruyorsa **_S_IFCHR** biti ayarlanır. *fd* sıradan bir dosyaya başvuruyorsa **_S_IFREG** biti ayarlanır. Okuma/yazma bitleri dosyanın izin moduna göre ayarlanır. **_S_IFCHR** ve diğer sabitler SYS\Stat.h'de tanımlanır. |
| **st_mtime** | Dosyanın son modifikasyonunun zamanı. |
| **st_nlink** | NTFS olmayan dosya sistemlerinde her zaman 1. |
| **st_rdev** | Eğer bir cihaz, *fd*; aksi takdirde 0. |
| **st_size** | Baytlar halindeki dosyanın boyutu. |

*FD* bir aygıta başvuruyorsa, **st_atime**, **st_ctime,** **st_mtime**ve **st_size** alanları anlamlı değildir.

Stat.h, Types.h'de tanımlanan [_dev_t](../../c-runtime-library/standard-types.md) türünü kullandığından, Code'a Stat.h'den önce Types.h'yi eklemeniz gerekir.

**__stat64** yapısını kullanan **_fstat64,** dosya oluşturma tarihlerinin 23:59:59, 31 Aralık 3000, UTC' ye kadar ifade edilmesine izin verir; diğer işlevler sadece 23:59:59 18 Ocak 2038, UTC tarihleri temsil ederken. Midnight, 1 Ocak 1970, tüm bu işlevler için tarih aralığının alt sınırıdır.

Bu işlevlerin varyasyonları 32 bit veya 64 bit zaman türlerini ve 32-bit veya 64 bit dosya uzunluklarını destekler. İlk sayısal sonek (**32** veya **64**) kullanılan zaman türünün boyutunu gösterir; ikinci sonek, dosya boyutunun 32 bit veya 64 bit tamsayı olarak temsil edilip edilmediğini belirten **i32** veya **i64'tür.**

**_fstat** **_fstat64i32**eşdeğerdir ve **_stat 64** bitlik bir süre **içerir.** **bu, _USE_32BIT_TIME_T** tanımlanmadıkça doğrudur ve bu durumda eski davranış geçerlidir; **_fstat** 32 bit lik bir süre kullanır ve **_stat 32** bitlik bir süre **içerir.** Aynı **_fstati64**için de geçerlidir.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="time-type-and-file-length-type-variations-of-_stat"></a>_stat Zaman Türü ve Dosya Uzunluğu Tür Varyasyonları

|İşlevler|_USE_32BIT_TIME_T tanımlanmış?|Zaman türü|Dosya uzunluğu türü|
|---------------|------------------------------------|---------------|----------------------|
|**_fstat**|Tanımlı değil|64 bit|32 bit|
|**_fstat**|Tanımlanan|32 bit|32 bit|
|**_fstat32**|Makro tanımından etkilenmez|32 bit|32 bit|
|**_fstat64**|Makro tanımından etkilenmez|64 bit|64 bit|
|**_fstati64**|Tanımlı değil|64 bit|64 bit|
|**_fstati64**|Tanımlanan|32 bit|64 bit|
|**_fstat32i64**|Makro tanımından etkilenmez|32 bit|64 bit|
|**_fstat64i32**|Makro tanımından etkilenmez|64 bit|32 bit|

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fstat**|\<sys/stat.h> \<ve sys/types.h>|
|**_fstat32**|\<sys/stat.h> \<ve sys/types.h>|
|**_fstat64**|\<sys/stat.h> \<ve sys/types.h>|
|**_fstati64**|\<sys/stat.h> \<ve sys/types.h>|
|**_fstat32i64**|\<sys/stat.h> \<ve sys/types.h>|
|**_fstat64i32**|\<sys/stat.h> \<ve sys/types.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

```C
// crt_fstat.c
// This program uses _fstat to report
// the size of a file named F_STAT.OUT.

#include <io.h>
#include <fcntl.h>
#include <time.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <errno.h>
#include <share.h>

int main( void )
{
   struct _stat buf;
   int fd, result;
   char buffer[] = "A line to output";
   char timebuf[26];
   errno_t err;

   _sopen_s( &fd,
             "f_stat.out",
             _O_CREAT | _O_WRONLY | _O_TRUNC,
             _SH_DENYNO,
             _S_IREAD | _S_IWRITE );
   if( fd != -1 )
      _write( fd, buffer, strlen( buffer ) );

   // Get data associated with "fd":
   result = _fstat( fd, &buf );

   // Check if statistics are valid:
   if( result != 0 )
   {
      if (errno == EBADF)
        printf( "Bad file descriptor.\n" );
      else if (errno == EINVAL)
        printf( "Invalid argument to _fstat.\n" );
   }
   else
   {
      printf( "File size     : %ld\n", buf.st_size );
      err = ctime_s(timebuf, 26, &buf.st_mtime);
      if (err)
      {
         printf("Invalid argument to ctime_s.");
         exit(1);
      }
      printf( "Time modified : %s", timebuf );
   }
   _close( fd );
}
```

```Output
File size     : 16
Time modified : Wed May 07 15:25:11 2003
```

## <a name="see-also"></a>Ayrıca bkz.

[Dosya Işleme](../../c-runtime-library/file-handling.md)<br/>
[_access, _waccess](access-waccess.md)<br/>
[_chmod, _wchmod](chmod-wchmod.md)<br/>
[_filelength, _filelengthi64](filelength-filelengthi64.md)<br/>
[_stat, _wstat Fonksiyonlar](stat-functions.md)<br/>
