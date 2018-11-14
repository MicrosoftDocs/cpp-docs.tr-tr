---
title: _fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32
ms.date: 11/04/2016
apiname:
- _fstat32
- _fstat64
- _fstati64
- _fstat
- _fstat64i32
- _fstat32i64
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: 36d8b0d6480266f86136119a470fb7af5859a5b8
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51331249"
---
# <a name="fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32"></a>_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32

Bir açık dosya hakkındaki bilgileri alır.

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

*FD*<br/>
Açık dosyanın dosya tanımlayıcısı.

*Arabellek*<br/>
Sonuçlarını depolamak için bir yapıya yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Dosya durumu bilgilerini aldıysanız 0 döndürür. -1 dönüş değeri bir hata olduğunu gösterir. Dosya tanımlayıcısı geçersizse veya *arabellek* olduğu **NULL**, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse **errno** ayarlanır **EBADF**, geçersiz dosya tanımlayıcısı olması durumunda veya çok **EINVAL**, *arabellek* olan **NULL**.

## <a name="remarks"></a>Açıklamalar

**_Fstat** işlevi ile ilişkili açık dosya hakkındaki bilgileri alır *fd* ve işaret ettiği yapısında depolar *arabellek*. **_Stat** SYS\Stat.h içinde tanımlanan yapısı, aşağıdaki alanları içerir.

|Alan|Açıklama|
|-|-|
| **st_atime** | Son dosya erişim zamanı. |
| **st_ctime** | Dosyanın oluşturulma saati. |
| **st_dev** | Bir cihaz, *fd*; Aksi durumda 0. |
| **st_mode** | Dosya modu bilgi bit maskesi. **_S_ıfchr** bit ayarlanmışsa *fd* bir cihazı gösterir. **_S_ıfreg** bit ayarlanmışsa *fd* sıradan bir dosyasına başvuruyor. Okuma/yazma BITS dosyanın izin Modu'nda göre ayarlanır. **_S_ıfchr** ve diğer sabitler SYS\Stat.h içinde tanımlanır. |
| **st_mtime** | Dosyanın son değiştirilme saati. |
| **st_nlink** | Her zaman 1 NTFS dışı dosya sistemlerine. |
| **st_rdev** | Bir cihaz, *fd*; Aksi durumda 0. |
| **st_size** | Dosyanın bayt cinsinden boyutu. |

Varsa *fd* bir cihaza başvuran **st_atime**, **st_ctime**, **st_mtime**, ve **st_size** alanlar anlamlı değildir.

STAT.h kullandığından [_dev_t](../../c-runtime-library/standard-types.md) yazın, Types.h içinde tanımlandığı, kodunuzda Types.h Stat.h önce içermelidir.

**_fstat64**, kullanan **__stat64** yapısı, 23:59:59, 31 Aralık, 3000, UTC; yukarı ifade edilecek tarihleri dosya oluşturma sağlarken diğer işlevleri yalnızca 23:59:59 18 Ocak tarihleri temsil eder 2038, UTC. Gece yarısı, 1 Ocak 1970, tüm bu işlevler için tarih aralığının alt sınırdır.

Bu işlevlerin değişimleri, 32 bit veya 64-bit saat türleri ve dosya 32 bit veya 64-bit uzunlukları destekler. İlk sayısal bir son eke (**32** veya **64**) zaman boyutu gösteren türü kullanılan dize; ikinci soneki geçerli **i32** veya **I64**, Dosya boyutu 32 bit veya 64-bit bir tamsayı olarak temsil edilen belirten.

**_fstat** eşdeğerdir **_fstat64i32**, ve **yapı** **_stat** 64-bit saati içerir. Bu sürece **_use_32bıt_tıme_t** tanımlanan, bu durumda eski davranışı; etkindir **_fstat** bir 32-bit saatini kullanır ve **yapı** **_stat** 32-bit saati içerir. Aynı true **_fstati64**.

### <a name="time-type-and-file-length-type-variations-of-stat"></a>Zaman türü ve dosya uzunluğu türü _stat çeşitleri

|İşlevler|_Use_32bıt_tıme_t tanımlanan?|Zaman türü|Dosya uzunluğu türü|
|---------------|------------------------------------|---------------|----------------------|
|**_fstat**|Tanımlı değil|64 bit|32 bit:|
|**_fstat**|Tanımlanan|32 bit:|32 bit:|
|**_fstat32**|Makro tanımı tarafından etkilenen değil|32 bit:|32 bit:|
|**_fstat64**|Makro tanımı tarafından etkilenen değil|64 bit|64 bit|
|**_fstati64**|Tanımlı değil|64 bit|64 bit|
|**_fstati64**|Tanımlanan|32 bit:|64 bit|
|**_fstat32i64**|Makro tanımı tarafından etkilenen değil|32 bit:|64 bit|
|**_fstat64i32**|Makro tanımı tarafından etkilenen değil|64 bit|32 bit:|

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fstat**|\<sys/STAT.h > ve \<sys/types.h >|
|**_fstat32**|\<sys/STAT.h > ve \<sys/types.h >|
|**_fstat64**|\<sys/STAT.h > ve \<sys/types.h >|
|**_fstati64**|\<sys/STAT.h > ve \<sys/types.h >|
|**_fstat32i64**|\<sys/STAT.h > ve \<sys/types.h >|
|**_fstat64i32**|\<sys/STAT.h > ve \<sys/types.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

[Dosya İşleme](../../c-runtime-library/file-handling.md)<br/>
[_access, _waccess](access-waccess.md)<br/>
[_chmod, _wchmod](chmod-wchmod.md)<br/>
[_filelength, _filelengthi64](filelength-filelengthi64.md)<br/>
[_stat, _wstat işlevleri](stat-functions.md)<br/>
