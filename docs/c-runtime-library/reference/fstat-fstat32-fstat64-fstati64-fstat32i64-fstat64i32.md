---
title: _fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 65d77bfdd7922387568ca8257e66f6e19dde1a35
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32404974"
---
# <a name="fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32"></a>_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32

Açık bir dosyayı hakkındaki bilgileri alır.

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
Sonuçların depolanacağı yapısına yönelik işaretçinin.

## <a name="return-value"></a>Dönüş Değeri

Dosya durumu bilgilerini aldıysanız 0 döndürür. Dönüş değeri-1 hata gösterir. Dosya tanımlayıcısı geçersizse veya *arabellek* olan **NULL**, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa **errno** ayarlanır **EBADF**, geçersiz bir dosya tanımlayıcısı söz konusu olduğunda veya çok **EINVAL**, *arabellek* olan **NULL**.

## <a name="remarks"></a>Açıklamalar

**_Fstat** işlevi ile ilişkili Dosya Aç hakkında bilgi edinir *fd* ve gösterdiği yapısı depolar *arabellek*. **_Stat** SYS\Stat.h içinde tanımlanan yapısı, aşağıdaki alanlar içeriyor.

|Alan|Açıklama|
|-|-|
**st_atime**|Son dosya erişimi zamanı.
**st_ctime**|Dosyanın oluşturulma saati.
**st_dev**|Bir aygıt, *fd*; Aksi halde 0.
**st_mode**|Bit maskesi dosya modu bilgi. **_S_ıfchr** bit ayarlanmışsa *fd* bir aygıta başvuruyor. **_S_ıfreg** bit ayarlanmışsa *fd* sıradan bir dosyaya başvuruyor. Okuma/yazma BITS dosyanın izin modunu göre ayarlanır. **_S_ıfchr** ve diğer sabitleri SYS\Stat.h tanımlanır.
**st_mtime**|Dosyanın son değiştirilme zamanı.
**st_nlink**|Her zaman 1 NTFS dışı dosya sistemlerine.
**st_rdev**|Bir aygıt, *fd*; Aksi halde 0.
**st_size**|Dosyanın bayt cinsinden boyutu.

Varsa *fd* bir aygıta başvuruyor **st_atime**, **st_ctime**, **st_mtime**, ve **st_size** alanlar anlamlı değil.

STAT.h kullandığından [_dev_t](../../c-runtime-library/standard-types.md) yazın, Types.h içinde tanımlandığı, kodunuzda Stat.h önce Types.h içermelidir.

**_fstat64**, kullanan **__stat64** yapısı, diğer işlevleri yalnızca 23:59:59 18 Ocak'ta aracılığıyla tarihleri gösteren 23:59:59, 31 Aralık 3000 UTC; yukarı ifade için dosya oluşturma tarihleri sağlarken 2038, UTC. Gece yarısından, 1 Ocak 1970'ten, bu işlevler için tarih aralığını alt sınırdır.

Bu işlevler varyasyonları 32 bit veya 64-bit saat türleri ve 32 bit veya 64-bit dosya uzunlukları destekler. İlk sayısal son ekten (**32** veya **64**) zaman boyutu gösteren türü; kullanılan ikinci soneki ya da **i32** veya **I64**, Dosya boyutu 32 bit veya 64 bit tamsayı olarak temsil edilir olup olmadığını belirten.

**_fstat** eşdeğerdir **_fstat64i32**, ve **yapısı** **_stat** 64-bit saati içerir. Bu durum geçerlidir sürece **_USE_32BIT_TIME_T** , bu durumda eski yürürlükte; davranıştır tanımlanır **_fstat** 32-bit zamanını kullanır ve **yapısı** **_stat** 32-bit saati içerir. Aynı için doğrudur **_fstati64**.

### <a name="time-type-and-file-length-type-variations-of-stat"></a>Saat türü ve dosya uzunluğu türü _stat varyasyonları

|İşlevler|Tanımlanan _USE_32BIT_TIME_T?|Zaman türü|Dosya uzunluğu türü|
|---------------|------------------------------------|---------------|----------------------|
|**_fstat**|Tanımlı değil|64 bit|32 bit:|
|**_fstat**|Tanımlı|32 bit:|32 bit:|
|**_fstat32**|Makro tanımı tarafından etkilenen değil|32 bit:|32 bit:|
|**_fstat64**|Makro tanımı tarafından etkilenen değil|64 bit|64 bit|
|**_fstati64**|Tanımlı değil|64 bit|64 bit|
|**_fstati64**|Tanımlı|32 bit:|64 bit|
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

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
