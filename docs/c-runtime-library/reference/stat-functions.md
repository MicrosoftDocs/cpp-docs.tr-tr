---
title: _stat, _stat32, _stat64, _stati64, _stat32i64, _stat64i32, _wstat, _wstat32, _wstat64, _wstati64, _wstat32i64, _wstat64i32
ms.date: 11/04/2016
api_name:
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
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 5a6e78c0d98871e4becbb5e7411d9c819e9d0596
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957943"
---
# <a name="_stat-_stat32-_stat64-_stati64-_stat32i64-_stat64i32-_wstat-_wstat32-_wstat64-_wstati64-_wstat32i64-_wstat64i32"></a>_stat, _stat32, _stat64, _stati64, _stat32i64, _stat64i32, _wstat, _wstat32, _wstat64, _wstati64, _wstat32i64, _wstat64i32

Bir dosya üzerinde durum bilgilerini alın.

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
Mevcut dosyanın veya dizinin yolunu içeren bir dize işaretçisi.

*arabelleğin*<br/>
Sonuçları depolayan yapıya yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri, dosya durum bilgileri elde edilmişse 0 değerini döndürür. -1 ' in dönüş değeri bir hatayı gösterir, bu durumda **errno** **, filename**veya Path bulunamadığını belirten bir hata gösterir. **EINVAL** dönüş değeri geçersiz bir parametreyi belirtiyor; **errno** , bu durumda **EINVAL** olarak da ayarlanır.

Bu ve diğer dönüş kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) .

Bir dosyadaki tarih damgası, **_stat32** veya **_wstat32**kullanmadığınız ya da **_Use_32bit_time_t**' i tanımlamış olmanız veya bu durumda bir tarih olması durumunda, 1 Ocak 1970, ve 23:59:59, 31 Aralık 3000, UTC 'den daha sonra temsil edilebilir. yalnızca 18 Ocak 2038, UTC 23:59:59 tarihine kadar temsil edilir.

## <a name="remarks"></a>Açıklamalar

**_Stat** işlevi, *yol* tarafından belirtilen dosya veya dizin hakkındaki bilgileri alır ve *arabelleğe*göre işaret eden yapıda depolar. **_stat** , çok baytlı karakter dize bağımsız değişkenlerini uygun şekilde otomatik olarak işler ve çok baytlı karakter dizilerini kullanımda olan çok baytlı kod sayfasına göre tanıyor.

**_wstat** , **_stat**; öğesinin geniş karakterli bir sürümüdür. **_wstat** için *yol* bağımsız değişkeni geniş karakterli bir dizedir. _wstat, çok baytlı karakter dizelerini işleyememesi dışında, **_wstat** ve **_stat** **aynı şekilde davranır** .

Bu işlevlerin çeşitlemeleri 32-veya 64 bit zaman türlerini ve 32 veya 64-bit dosya uzunluklarını destekler. İlk sayısal sonek (**32** veya **64**) kullanılan zaman türü boyutunu belirtir; İkinci sonek, dosya boyutunun 32-bit veya 64 bit tamsayı olarak temsil edilip edilmeyeceğini gösteren **i32** veya **i64**.

**_stat** **_stat64i32**ile eşdeğerdir ve **struct** **_stat** 64 bitlik bir süre içerir. **_Use_32bit_time_t** tanımlanmadıkça bu durum geçerlidir; bu durumda eski davranış geçerli olur; **_stat** 32 bitlik bir süre kullanır ve **Yapı** **_stat** bir 32 bit zaman içerir. Aynı **_stati64**için de geçerlidir.

> [!NOTE]
> **_wstat** , Windows Vista sembolik bağlantılarıyla çalışmaz. Bu durumlarda, **_wstat** her zaman 0 ' ın bir dosya boyutunu rapor eder. **_stat** sembolik bağlantılarla doğru şekilde çalışır.

Bu işlev, parametrelerini doğrular. *Yolun* veya *arabelleğin* ikisi de **null**ise, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır.

### <a name="time-type-and-file-length-type-variations-of-_stat"></a>_Stat 'nin saat türü ve dosya uzunluğu türü çeşitleri

|İşlevler|_USE_32BIT_TIME_T tanımlandı mı?|Zaman türü|Dosya uzunluğu türü|
|---------------|------------------------------------|---------------|----------------------|
|**_stat**, **_wstat**|Tanımsız|64 bit|32 bit:|
|**_stat**, **_wstat**|Tanımlı|32 bit:|32 bit:|
|**_stat32**, **_wstat32**|Makro tanımından etkilenmedi|32 bit:|32 bit:|
|**_stat64**, **_wstat64**|Makro tanımından etkilenmedi|64 bit|64 bit|
|**_stati64**, **_wstati64**|Tanımsız|64 bit|64 bit|
|**_stati64**, **_wstati64**|Tanımlı|32 bit:|64 bit|
|**_stat32i64**, **_wstat32i64**|Makro tanımından etkilenmedi|32 bit:|64 bit|
|**_stat64i32**, **_wstat64i32**|Makro tanımından etkilenmedi|64 bit|32 bit:|

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNıCODE & _MBCS tanımlı değil|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstat**|**_stat**|**_stat**|**_wstat**|
|**_tstat64**|**_stat64**|**_stat64**|**_wstat64**|
|**_tstati64**|**_stati64**|**_stati64**|**_wstati64**|
|**_tstat32i64**|**_stat32i64**|**_stat32i64**|**_wstat32i64**|
|**_tstat64i32**|**_stat64i32**|**_stat64i32**|**_wstat64i32**|

SYS\STAT'TE tanımlanan **_stat** yapısı. H, aşağıdaki alanları içerir.

|Alan||
|-|-|
| **st_gid** | Dosyanın sahibi olan grubun sayısal tanımlayıcısı (UNIX 'e özgü) Bu alan, her zaman Windows sistemlerinde sıfırdır. Yeniden yönlendirilen bir dosya Windows dosyası olarak sınıflandırılır. |
| **st_atime** | Dosyaya son erişim zamanı. NTFS 'de geçerlidir ancak FAT biçimli disk sürücülerinde değildir. |
| **st_ctime** | Dosya oluşturma zamanı. NTFS 'de geçerlidir ancak FAT biçimli disk sürücülerinde değildir. |
| **st_dev** | Dosyayı içeren diskin sürücü numarası ( **st_rdev**ile aynı). |
| **st_ino** | Dosya (UNIX 'e özgü) için bilgi düğümünün ( **INode**) sayısı. UNIX dosya sistemlerinde, **inode** dosya tarih ve saat damgalarını, izinleri ve içeriği tanımlar. Dosyalar birbirine sabit bağlandığında, aynı **INode**öğesini paylaşır. **INode**ve bu nedenle **st_ino**, FAT, HPFS veya NTFS dosya sistemlerinde bir anlamı yoktur. |
| **st_mode** | Dosya modu bilgileri için bit maskesi. **_S_ifdir** biti, *yol* bir dizin belirtiyorsa ayarlanır; *yol* sıradan bir dosya veya cihaz belirtiyorsa **_S_ifreg** bit ayarlanır. Kullanıcı okuma/yazma bitleri dosyanın izin moduna göre ayarlanır; Kullanıcı yürütme bitleri dosya adı uzantısına göre ayarlanır. |
| **st_mtime** | Dosyanın son değiştirilme zamanı. |
| **st_nlink** | NTFS olmayan dosya sistemlerinde her zaman 1. |
| **st_rdev** | Dosyayı içeren diskin sürücü numarası ( **st_dev**ile aynı). |
| **st_size** | Dosyanın bayt cinsinden boyutu; **i64** soneki olan çeşitlemeler için 64 bitlik bir tamsayı. |
| **st_uid** | Dosyanın sahibi olan kullanıcının sayısal tanımlayıcısı (UNIX 'e özgü). Bu alan Windows sistemlerinde her zaman sıfır olur. Yeniden yönlendirilen bir dosya Windows dosyası olarak sınıflandırılır. |

*Yol* bir cihaza başvuruyorsa, **_stat** yapısındaki **st_size**, çeşitli saat alanları, **st_dev**ve **st_rdev** alanları anlamsız bir şekilde düşüktür. Çünkü STAT. H, türlerde tanımlanan [_dev_t](../../c-runtime-library/standard-types.md) türünü kullanır. H, TÜRLERI dahil etmeniz gerekir. STAT 'dan önce H. U kodunuzda H.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgiler|
|-------------|---------------------|----------------------|
|**_stat**, **_stat32**, **_stat64**, **_stati64**, **_stat32i64**, **_stat64i32**|\<sys/Types. h > ardından \<sys/stat. h >|\<errno. h >|
|**_wstat**, **_wstat32**, **_wstat64**, **_wstati64**, **_wstat32i64**, **_wstat64i32**|\<sys/Types. h > ardından \<sys/stat. h > veya \<wchar. h >|\<errno. h >|

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
