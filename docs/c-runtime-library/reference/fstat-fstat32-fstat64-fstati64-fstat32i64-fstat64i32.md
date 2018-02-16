---
title: _fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c9518a0ea841a252717c225df7f07deba3a1ffbf
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32"></a>_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32
Açık bir dosyayı hakkındaki bilgileri alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
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
  
#### <a name="parameters"></a>Parametreler  
 `fd`  
 Açık dosyanın dosya tanımlayıcısı.  
  
 `buffer`  
 Sonuçların depolanacağı yapısına yönelik işaretçinin.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Dosya durumu bilgilerini aldıysanız 0 döndürür. Dönüş değeri-1 hata gösterir. Dosya tanımlayıcısı geçersizse veya `buffer` olan `NULL`, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa `errno` ayarlanır `EBADF`, geçersiz bir dosya tanımlayıcısı söz konusu olduğunda veya çok `EINVAL`, `buffer` olan `NULL`.  
  
## <a name="remarks"></a>Açıklamalar  
 `_fstat` İşlevi ile ilişkili Dosya Aç hakkında bilgi edinir `fd` ve gösterdiği yapısı depolar `buffer`. `_stat` SYS\Stat.h içinde tanımlanan yapısı, aşağıdaki alanlar içeriyor.  
  
 `st_atime`  
 Son dosya erişimi zamanı.  
  
 `st_ctime`  
 Dosyanın oluşturulma saati.  
  
 `st_dev`  
 Bir aygıt, `fd`; Aksi halde 0.  
  
 `st_mode`  
 Bit maskesi dosya modu bilgi. `_S_IFCHR` Bit ayarlanmışsa `fd` bir aygıta başvuruyor. `_S_IFREG` Bit ayarlanmışsa `fd` sıradan bir dosyaya başvuruyor. Okuma/yazma BITS dosyanın izin modunu göre ayarlanır. `_S_IFCHR` ve diğer sabitleri SYS\Stat.h tanımlanır.  
  
 `st_mtime`  
 Dosyanın son değiştirilme zamanı.  
  
 `st_nlink`  
 Her zaman 1 NTFS dışı dosya sistemlerine.  
  
 `st_rdev`  
 Bir aygıt, `fd`; Aksi halde 0.  
  
 `st_size`  
 Dosyanın bayt cinsinden boyutu.  
  
 Varsa `fd` bir aygıta başvuruyor `st_atime`, `st_ctime`, `st_mtime`, ve `st_size` alanlar anlamlı değildir.  
  
 STAT.h kullandığından [_dev_t](../../c-runtime-library/standard-types.md) yazın, Types.h içinde tanımlandığı, kodunuzda Stat.h önce Types.h içermelidir.  
  
 `_fstat64`, kullanan `__stat64` yapısı, diğer işlevleri yalnızca ile 23:59:59 18 Ocak 2038, UTC tarihleri gösteren sağlarken dosya oluşturma tarihleri ayarlama 23:59:59, 31 Aralık 3000 UTC; ifade edilebilir. Gece yarısından, 1 Ocak 1970'ten, bu işlevler için tarih aralığını alt sınırdır.  
  
 Bu işlevler varyasyonları 32 bit veya 64-bit saat türleri ve 32 bit veya 64-bit dosya uzunlukları destekler. İlk sayısal son ekten (`32` veya `64`) zaman boyutu gösteren türü; kullanılan ikinci soneki ya da `i32` veya `i64`, belirten olup dosya boyutu 32 bit veya 64 bit tamsayı olarak temsil edilir.  
  
 `_fstat` eşdeğer olan `_fstat64i32`, ve `struct _stat` 64-bit saati içerir. Bu durum geçerlidir sürece `_USE_32BIT_TIME_T` , bu durumda eski yürürlükte; davranıştır tanımlanır `_fstat` 32-bit zamanını kullanır ve `struct _stat` 32-bit saati içerir. Aynı için doğrudur `_fstati64`.  
  
### <a name="time-type-and-file-length-type-variations-of-stat"></a>Saat türü ve dosya uzunluğu türü _stat varyasyonları  
  
|İşlevler|Tanımlanan _USE_32BIT_TIME_T?|Zaman türü|Dosya uzunluğu türü|  
|---------------|------------------------------------|---------------|----------------------|  
|`_fstat`|Tanımlı değil|64 bit|32 bit:|  
|`_fstat`|Tanımlı|32 bit:|32 bit:|  
|`_fstat32`|Makro tanımı tarafından etkilenen değil|32 bit:|32 bit:|  
|`_fstat64`|Makro tanımı tarafından etkilenen değil|64 bit|64 bit|  
|`_fstati64`|Tanımlı değil|64 bit|64 bit|  
|`_fstati64`|Tanımlı|32 bit:|64 bit|  
|`_fstat32i64`|Makro tanımı tarafından etkilenen değil|32 bit:|64 bit|  
|`_fstat64i32`|Makro tanımı tarafından etkilenen değil|64 bit|32 bit:|  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|Gerekli başlık|  
|--------------|---------------------|  
|`_fstat`|\<sys/STAT.h > ve \<sys/types.h >|  
|`_fstat32`|\<sys/STAT.h > ve \<sys/types.h >|  
|`_fstat64`|\<sys/STAT.h > ve \<sys/types.h >|  
|`_fstati64`|\<sys/STAT.h > ve \<sys/types.h >|  
|`_fstat32i64`|\<sys/STAT.h > ve \<sys/types.h >|  
|`_fstat64i32`|\<sys/STAT.h > ve \<sys/types.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dosya işleme](../../c-runtime-library/file-handling.md)   
 [_access, _waccess](../../c-runtime-library/reference/access-waccess.md)   
 [_chmod, _wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [_filelength, _filelengthi64](../../c-runtime-library/reference/filelength-filelengthi64.md)   
 [_stat, _wstat işlevleri](../../c-runtime-library/reference/stat-functions.md)