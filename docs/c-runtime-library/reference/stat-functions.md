---
title: _stat, _stat32, _stat64, _stati64, _stat32i64, _stat64i32, _wstat, _wstat32, _wstat64, _wstati64, _wstat32i64, _wstat64i32 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wstat64
- _stati64
- _stat32
- _stat32i64
- _stat
- _wstati64
- _wstat32
- _wstat64i32
- _wstat
- _stat64
- _stat64i32
- _wstat32i64
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
- tstat32
- tstat
- _tstat64i32
- tstati64
- _wstat64
- _wstat32
- wstati64
- tstat64
- _stati64
- _wstat
- wstat64i32
- stat32i64
- tstat32i64
- _tstat
- _wstati64
- _tstati64
- _wstat32i64
- wstat32
- _wstat64i32
- _stat
- _tstat32
- stat64i32
- wstat64
- stat
- _stat32i64
- _stat32
- stati64
- wstat
- _stat64i32
- stat32
- _tstat32i64
- tstat64i32
- _tstat64
- _stat64
- stat/_stat
- stat/_stat32
- stat/_stat64
- stat/_stati64
- stat/_stat32i64
- stat/_stat64i32
- stat/_wstat
- stat/_wstat32
- stat/_wstat64
- stat/_wstati64
- stat/_wstat32i64
- stat/_wstat64i32
dev_langs: C++
helpviewer_keywords:
- files [C++], status information
- _stat function
- _wstat function
- _stat64i32 function
- tstat function
- _tstat64i32 function
- _stati64 function
- _stat64 function
- tstati64 function
- wstati64 function
- wstat64 function
- _wstat64i32 function
- _tstat32i64 function
- _stat32i64 function
- stat function
- status of files
- _tstat32 function
- tstat64 function
- _wstat64 function
- _tstat function
- _stat32 function
- wstat function
- _wstat32i64 function
- _tstati64 function
- _wstat32 function
- stat64 function
- stati64 function
- _wstati64 function
- _tstat64 function
- files [C++], getting status information
ms.assetid: 99a75ae6-ff26-47ad-af70-5ea7e17226a5
caps.latest.revision: "26"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 18cfdda310149c18ef8983b10afb5c901b256510
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="stat-stat32-stat64-stati64-stat32i64-stat64i32-wstat-wstat32-wstat64-wstati64-wstat32i64-wstat64i32"></a>_stat, _stat32, _stat64, _stati64, _stat32i64, _stat64i32, _wstat, _wstat32, _wstat64, _wstati64, _wstat32i64, _wstat64i32
Durum bilgileri, bir dosyada alın.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _stat(  
   const char *path,  
   struct _stat *buffer   
);  
int _stat32(  
   const char *path,  
   struct __stat32 *buffer   
);  
int _stat64(  
   const char *path,  
   struct __stat64 *buffer   
);  
int _stati64(  
   const char *path,  
   struct _stati64 *buffer   
);  
int _stat32i64(  
   const char *path,  
   struct _stat32i64 *buffer   
);  
int _stat64i32(  
   const char *path,  
   struct _stat64i32 *buffer   
);  
int _wstat(  
   const wchar_t *path,  
   struct _stat *buffer   
);  
int _wstat32(  
   const wchar_t *path,  
   struct __stat32 *buffer   
);  
int _wstat64(  
   const wchar_t *path,  
   struct __stat64 *buffer   
);  
int _wstati64(  
   const wchar_t *path,  
   struct _stati64 *buffer   
);  
int _wstat32i64(  
   const wchar_t *path,  
   struct _stat32i64 *buffer   
);  
int _wstat64i32(  
   const wchar_t *path,  
   struct _stat64i32 *buffer   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `path`  
 Var olan dosya veya dizin yolunu içeren bir dize işaretçi.  
  
 `buffer`  
 Sonuçları depolar yapısına yönelik işaretçinin.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Dosya durumu bilgilerini aldıysanız bu işlevlerin her biri 0 döndürür. Dönüş değeri-1, bu durumda bir hata gösterir `errno` ayarlanır `ENOENT`, dosya adı veya yolu bulunamadığından olduğunu gösteren. Dönüş değeri `EINVAL` geçersiz bir parametre; gösterir `errno` de ayarlamak `EINVAL` bu durumda.  
  
 Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu ve diğer hakkında daha fazla bilgi için dönüş kodları.  
  
 Kullanmadığınız sürece, 1 Ocak 1970 yarısı daha ve 23:59:59 31 Aralık 3000 UTC, önce sonraki ise, bir dosyada tarih damgası temsil edilebilir `_stat32` veya `_wstat32`, veya tanımlamış olduğunuz `_USE_32BIT_TIME_T`, yalnızca kadar tarihi bu durumda gösterilebilir 23:59:59 18 Ocak 2038, UTC.  
  
## <a name="remarks"></a>Açıklamalar  
 `_stat` İşlevi dosya veya dizin tarafından belirtilen hakkında bilgi edinir `path` ve gösterdiği yapısı depolar `buffer`. `_stat`çok baytlı karakter sıralarının şu anda kullanımda birden çok baytlı kod sayfasına göre algılamayı çok baytlı karakter dizesi bağımsız değişkenleri uygun şekilde otomatik olarak yönetir.  
  
 `_wstat`bir joker karakter sürümü `_stat`; `path` bağımsız değişkeni `_wstat` bir joker karakter dizesidir. `_wstat`ve `_stat` durumlar dışında aynı şekilde davranır `_wstat` çok baytlı karakter dizeleri işlemez.  
  
 Bu işlevlerin Çeşitlemeler 32 veya 64 bit saat türleri ve 32 veya 64 bit dosya uzunlukları destekler. İlk sayısal son ekten (`32` veya `64`) zaman boyutu gösteren türü; kullanılan ikinci soneki ya da `i32` veya `i64`, belirten olup dosya boyutu 32 bit veya 64 bit tamsayı olarak temsil edilir.  
  
 `_stat`eşdeğer olan `_stat64i32`, ve `struct _stat` 64-bit saati içerir. Bu durum geçerlidir sürece `_USE_32BIT_TIME_T` , bu durumda eski yürürlükte; davranıştır tanımlanır `_stat` 32-bit zamanını kullanır ve `struct _stat` 32-bit saati içerir. Aynı için doğrudur `_stati64`.  
  
> [!NOTE]
>  `_wstat`ile çalışmaz [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] sembolik bağlantılar. Bu durumda, `_wstat` her zaman bir dosya boyutu 0 rapor eder. `_stat`sembolik bağlantılar ile düzgün çalışır.  
  
 Bu işlev parametrelerini doğrular. Her iki `path` veya `buffer` olan `NULL`, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md).  
  
### <a name="time-type-and-file-length-type-variations-of-stat"></a>Saat türü ve dosya uzunluğu türü _stat varyasyonları  
  
|İşlevler|Tanımlanan _USE_32BIT_TIME_T?|Zaman türü|Dosya uzunluğu türü|  
|---------------|------------------------------------|---------------|----------------------|  
|`_stat`, `_wstat`|Tanımlı değil|64 bit|32 bit:|  
|`_stat`, `_wstat`|Tanımlı|32 bit:|32 bit:|  
|`_stat32`, `_wstat32`|Makro tanımı tarafından etkilenen değil|32 bit:|32 bit:|  
|`_stat64`, `_wstat64`|Makro tanımı tarafından etkilenen değil|64 bit|64 bit|  
|`_stati64`, `_wstati64`|Tanımlı değil|64 bit|64 bit|  
|`_stati64`, `_wstati64`|Tanımlı|32 bit:|64 bit|  
|`_stat32i64`, `_wstat32i64`|Makro tanımı tarafından etkilenen değil|32 bit:|64 bit|  
|`_stat64i32`, `_wstat64i32`|Makro tanımı tarafından etkilenen değil|64 bit|32 bit:|  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tstat`|`_stat`|`_stat`|`_wstat`|  
|`_tstat64`|`_stat64`|`_stat64`|`_wstat64`|  
|`_tstati64`|`_stati64`|`_stati64`|`_wstati64`|  
|`_tstat32i64`|`_stat32i64`|`_stat32i64`|`_wstat32i64`|  
|`_tstat64i32`|`_stat64i32`|`_stat64i32`|`_wstat64i32`|  
  
 `_stat` SYS\STAT içinde tanımlanan yapısı. H, aşağıdaki alanları içerir.  
  
 `st_gid`  
 Bu alan (UNIX özgü) dosyasına sahip grubunun sayısal tanıtıcısı her zaman Windows sistemlerinde sıfır olacak. Yönlendirilen bir dosyadan bir Windows dosya olarak sınıflandırılır.  
  
 `st_atime`  
 Dosyanın son erişim zamanı. Geçerli NTFS ancak çalıştırılmadı FAT biçimlendirmesine sahip disk sürücülerine.  
  
 `st_ctime`  
 Dosya oluşturulma zamanı. Geçerli NTFS ancak çalıştırılmadı FAT biçimlendirmesine sahip disk sürücülerine.  
  
 `st_dev`  
 Dosyayı içeren disk sayısı sürücü (aynı `st_rdev`).  
  
 `st_ino`  
 Bilgi düğüm sayısı ( `inode`) (UNIX özgü) dosyası için. UNIX dosya sistemlerindeki `inode` dosya tarih ve zaman damgaları, izinleri ve içeriği açıklar. Dosyaların sabit birbirine bağlı olduğunda, aynı paylaştıkları `inode`. `inode`, Bu nedenle `st_ino`, FAT, HPFS veya NTFS dosya sistemlerinde bir anlamı yoktur.  
  
 `st_mode`  
 Bit maskesi dosya modu bilgi. `_S_IFDIR` Bit ayarlanmışsa `path` bir dizini belirtir; `_S_IFREG` bit ayarlanmışsa `path` sıradan bir dosya veya bir aygıt belirtir. Kullanıcı okuma/yazma BITS dosyanın izin modunu göre ayarlanır; Kullanıcı yürütme BITS dosya adı uzantısına göre ayarlanır.  
  
 `st_mtime`  
 Dosyanın son değiştirilme zamanı.  
  
 `st_nlink`  
 Her zaman 1 NTFS dışı dosya sistemlerine.  
  
 `st_rdev`  
 Dosyayı içeren disk sayısı sürücü (aynı `st_dev`).  
  
 `st_size`  
 Dosyanın bayt cinsinden boyutu; ile değişimler için 64-bit tamsayı `i64` soneki**.**  
  
 `st_uid`  
 Dosya (UNIX özgü) sahibi kullanıcı sayısal tanımlayıcısı. Bu alan, her zaman Windows sistemlerinde sıfır olacak. Yönlendirilen bir dosyadan bir Windows dosya olarak sınıflandırılır.  
  
 Varsa `path` bir aygıta başvuruyor `st_size`, çeşitli saat alanları `st_dev`, ve `st_rdev` alanlarını `_stat` yapısı anlamsız. Çünkü STAT. H kullanır [_dev_t](../../c-runtime-library/standard-types.md) türü olarak tanımlanmış tür. H TÜRLERİ eklemeniz gerekir. H STAT önce. H kodunuzda.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|  
|-------------|---------------------|----------------------|  
|`_stat`, `_stat32`, `_stat64`, `_stati64`, `_stat32i64`, `_stat64i32`|\<sys/Types.h > arkasından \<sys/stat.h >|\<errno.h >|  
|`_wstat`, `_wstat32`, `_wstat64`, `_wstati64`, `_wstat32i64`, `_wstat64i32`|\<sys/Types.h > arkasından \<sys/stat.h > veya \<wchar.h >|\<errno.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_stat.c  
// This program uses the _stat function to  
// report information about the file named crt_stat.c.  
  
#include <time.h>  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <stdio.h>  
#include <errno.h>  
  
int main( void )  
{  
   struct _stat buf;  
   int result;  
   char timebuf[26];  
   char* filename = "crt_stat.c";  
   errno_t err;  
  
   // Get data associated with "crt_stat.c":   
   result = _stat( filename, &buf );  
  
   // Check if statistics are valid:   
   if( result != 0 )  
   {  
      perror( "Problem getting information" );  
      switch (errno)  
      {  
         case ENOENT:  
           printf("File %s not found.\n", filename);  
           break;  
         case EINVAL:  
           printf("Invalid parameter to _stat.\n");  
           break;  
         default:  
           /* Should never be reached. */  
           printf("Unexpected error in _stat.\n");  
      }  
   }  
   else  
   {  
      // Output some of the statistics:   
      printf( "File size     : %ld\n", buf.st_size );  
      printf( "Drive         : %c:\n", buf.st_dev + 'A' );  
      err = ctime_s(timebuf, 26, &buf.st_mtime);  
      if (err)  
      {  
         printf("Invalid arguments to ctime_s.");  
         exit(1);  
      }  
      printf( "Time modified : %s", timebuf );  
   }  
}  
```  
  
```Output  
File size     : 732  
Drive         : C:  
Time modified : Thu Feb 07 14:39:36 2002  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dosya işleme](../../c-runtime-library/file-handling.md)   
 [_access, _waccess](../../c-runtime-library/reference/access-waccess.md)   
 [_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)