---
title: _stat, _stat32, _stat64, _stati64, _stat32i64, _stat64i32, _wstat, _wstat32, _wstat64, _wstati64, _wstat32i64, _wstat64i32
ms.date: 11/04/2016
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
ms.openlocfilehash: 316012479ec374cc5f40061384475008fe04e331
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50637287"
---
# <a name="stat-stat32-stat64-stati64-stat32i64-stat64i32-wstat-wstat32-wstat64-wstati64-wstat32i64-wstat64i32"></a>_stat, _stat32, _stat64, _stati64, _stat32i64, _stat64i32, _wstat, _wstat32, _wstat64, _wstati64, _wstat32i64, _wstat64i32

Dosya durumu bilgilerini alın.

## <a name="syntax"></a>Sözdizimi

```C
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

### <a name="parameters"></a>Parametreler

*Yolu*<br/>
Var olan dosya veya dizin yolunu içeren bir dize işaretçisi.

*Arabellek*<br/>
Sonuçlarını depolar yapıya yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Dosya durumu bilgilerini edindiyseniz, bu işlevlerin her biri 0 döndürür. -1 değeri, bu durumda bir hata belirtir **errno** ayarlanır **ENOENT**, dosya adı veya yolu bulunamadı olduğunu gösteren. Dönüş değeri **EINVAL** ; geçersiz bir parametre belirtir **errno** ayrıca kümesine **EINVAL** böyle bir durumda.

Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu ve diğer hakkında daha fazla bilgi için dönüş kodları.

Kullandığınız sürece, 1 Ocak 1970 gece yarısı ve 23:59:59, 31 Aralık, 3000, UTC önce daha geç ise bir dosya çubuğunda tarih damgası temsil edilebilir **_stat32** veya **_wstat32**, veya tanımlamış **_ USE_32BIT_TIME_T**, bu durumda yalnızca 23:59:59 kadar 18 Ocak 2038, UTC tarihi gösterilebilir.

## <a name="remarks"></a>Açıklamalar

**_Stat** işlevi dosya veya dizin tarafından belirtilen hakkında bilgi edinir *yolu* ve işaret ettiği yapısında depolar *arabellek*. **_stat** çok baytlı karakter sıralarını şu anda çok baytlı kod sayfasına göre algılamayı çok baytlı karakter dizesi bağımsız değişkenleri uygun şekilde otomatik olarak işler.

**_wstat** geniş karakterli sürümüdür **_stat**; *yolu* bağımsız değişkeni **_wstat** geniş karakterli bir dizedir. **_wstat** ve **_stat** aynı şekilde davranır **_wstat** çok baytlı karakter dizelerini işlemez.

Bu işlevlerin çeşitlemeleri saat türleri 32 veya 64 bit ve 32 veya 64 bit dosya uzunluklarını destekler. İlk sayısal bir son eke (**32** veya **64**) zaman boyutu gösteren türü kullanılan dize; ikinci soneki geçerli **i32** veya **I64**, Dosya boyutu 32 bit veya 64-bit bir tamsayı olarak temsil edilen belirten.

**_stat** eşdeğerdir **_stat64i32**, ve **yapı** **_stat** 64-bit saati içerir. Bu sürece **_use_32bıt_tıme_t** tanımlanan, bu durumda eski davranışı; etkindir **_stat** bir 32-bit saatini kullanır ve **yapı** **_stat** 32-bit saati içerir. Aynı true **_stati64**.

> [!NOTE]
> **_wstat** Windows Vista ile simgesel bağlantılar çalışmaz. Bu gibi durumlarda, **_wstat** her zaman bir dosya boyutu 0'ın rapor eder. **_stat** sembolik bağlantılar ile düzgün çalışır.

Bu işlev, parametrelerini doğrular. Ya da *yolu* veya *arabellek* olduğu **NULL**, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md).

### <a name="time-type-and-file-length-type-variations-of-stat"></a>Zaman türü ve dosya uzunluğu türü _stat çeşitleri

|İşlevler|_Use_32bıt_tıme_t tanımlanan?|Zaman türü|Dosya uzunluğu türü|
|---------------|------------------------------------|---------------|----------------------|
|**_stat**, **_wstat**|Tanımlı değil|64 bit|32 bit:|
|**_stat**, **_wstat**|Tanımlanan|32 bit:|32 bit:|
|**_stat32**, **_wstat32**|Makro tanımı tarafından etkilenen değil|32 bit:|32 bit:|
|**_stat64**, **_wstat64**|Makro tanımı tarafından etkilenen değil|64 bit|64 bit|
|**_stati64**, **_wstati64**|Tanımlı değil|64 bit|64 bit|
|**_stati64**, **_wstati64**|Tanımlanan|32 bit:|64 bit|
|**_stat32i64**, **_wstat32i64**|Makro tanımı tarafından etkilenen değil|32 bit:|64 bit|
|**_stat64i32**, **_wstat64i32**|Makro tanımı tarafından etkilenen değil|64 bit|32 bit:|

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstat**|**_stat**|**_stat**|**_wstat**|
|**_tstat64**|**_stat64**|**_stat64**|**_wstat64**|
|**_tstati64**|**_stati64**|**_stati64**|**_wstati64**|
|**_tstat32i64**|**_stat32i64**|**_stat32i64**|**_wstat32i64**|
|**_tstat64i32**|**_stat64i32**|**_stat64i32**|**_wstat64i32**|

**_Stat** SYS\STAT içinde tanımlanan yapısı. H, aşağıdaki alanları içerir.

|Alan||
|-|-|
**st_gid**|Bu alan ' % s'dosyasına (UNIX özgü) sahip grup sayısal tanıtıcısı her zaman Windows sistemlerinde sıfır olur. Yeniden yönlendirilen bir dosya, bir Windows dosya olarak sınıflandırılır.
**st_atime**|Dosyanın son erişim zamanı. Geçerli NTFS ancak çalıştırılmadı FAT biçimlendirmesine sahip disk sürücülerine.
**st_ctime**|Dosya oluşturulma saati. Geçerli NTFS ancak çalıştırılmadı FAT biçimlendirmesine sahip disk sürücülerine.
**st_dev**|Dosyayı içeren disk sayısı sürücü (aynı **st_rdev**).
**st_ino**|Bilgi düğümü sayısı ( **Inode**) ' % s'dosyası (UNIX özgü). UNIX dosya sistemlerindeki **Inode** dosya tarih ve zaman damgaları, izinleri ve içeriği açıklanmaktadır. Dosyaları sabit birbirine bağlı olduğunda, aynı paylaştıkları **Inode**. **Inode**ve bu nedenle **st_ino**, FAT, HPFS veya NTFS dosya sisteminde bir anlamı yoktur.
**st_mode**|Dosya modu bilgi bit maskesi. **_S_ıfdır** bit ayarlanmışsa *yolu* bir dizini belirtir; **_s_ıfreg** bit ayarlanmışsa *yolu* sıradan bir dosya ya da bir cihaz belirtir. Kullanıcı okuma/yazma BITS dosyanın izin Modu'nda göre ayarlanır; Kullanıcı yürütme BITS dosya adı uzantısına göre ayarlanır.
**st_mtime**|Dosyanın son değiştirilme saati.
**st_nlink**|Her zaman 1 NTFS dışı dosya sistemlerine.
**st_rdev**|Dosyayı içeren disk sayısı sürücü (aynı **st_dev**).
**st_size**|Dosyanın bayt cinsinden boyutunu; bir 64-bit tamsayı ile çeşitleri için **I64** soneki.
**st_uid**|Sayısal dosyasına (UNIX özgü) sahip kullanıcı tanımlayıcısı. Bu alan, her zaman Windows sistemlerinde sıfır olur. Yeniden yönlendirilen bir dosya, bir Windows dosya olarak sınıflandırılır.

Varsa *yolu* bir cihaza başvuran **st_size**, çeşitli saat alanları **st_dev**, ve **st_rdev** alanlarını **_stat**  yapısı anlamsız. Çünkü STAT. H kullandığı [_dev_t](../../c-runtime-library/standard-types.md) türü içinde tanımlanmış TÜRLERİ. H TÜRLERİ eklemeniz gerekir. STAT önce H. Kodunuzda H.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üst bilgiler|
|-------------|---------------------|----------------------|
|**_stat**, **_stat32**, **_stat64**, **_stati64**, **_stat32i64**, **_stat64i32**|\<sys/Types.h > ardından \<sys/stat.h >|\<errno.h >|
|**_wstat**, **_wstat32**, **_wstat64**, **_wstati64**, **_wstat32i64**, **_wstat64i32**|\<sys/Types.h > ardından \<sys/stat.h > veya \<wchar.h >|\<errno.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
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

## <a name="see-also"></a>Ayrıca bkz.

[Dosya İşleme](../../c-runtime-library/file-handling.md)<br/>
[_access, _waccess](access-waccess.md)<br/>
[_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_setmbcp](setmbcp.md)<br/>
