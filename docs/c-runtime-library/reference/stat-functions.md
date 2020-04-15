---
title: _stat, _stat32, _stat64, _stati64, _stat32i64, _stat64i32, _wstat, _wstat32, _wstat64, _wstati64, _wstat32i64, _wstat64i32
ms.date: 4/2/2020
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
- _o__stat32
- _o__stat32i64
- _o__stat64
- _o__stat64i32
- _o__wstat32
- _o__wstat32i64
- _o__wstat64
- _o__wstat64i32
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
ms.openlocfilehash: 32a96a93eb8a18e366ac7a075b414dbca732fb61
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81355413"
---
# <a name="_stat-_stat32-_stat64-_stati64-_stat32i64-_stat64i32-_wstat-_wstat32-_wstat64-_wstati64-_wstat32i64-_wstat64i32"></a>_stat, _stat32, _stat64, _stati64, _stat32i64, _stat64i32, _wstat, _wstat32, _wstat64, _wstati64, _wstat32i64, _wstat64i32

Dosyada durum bilgilerini alın.

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
Varolan dosya veya dizin yolunu içeren bir dize işaretçisi.

*Arabellek*<br/>
Sonuçları depolayan yapıişaretçisi.

## <a name="return-value"></a>Dönüş Değeri

Dosya durumu bilgileri elde edilirse, bu işlevlerin her biri 0 döndürür. -1'in geri dönüş değeri, bu durumda **errno'nun** **ENOENT**olarak ayarlandığı ve dosya adının veya yolun bulunamadığını belirten bir hatayı gösterir. **EINVAL'ın** geri dönüş değeri geçersiz bir parametreyi gösterir; **errno** da bu durumda **EINVAL** olarak ayarlanır.

Bu ve diğer iade kodları hakkında daha fazla bilgi için [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bakın.

Bir dosyadaki tarih damgası gece yarısından sonra, 1 Ocak 1970'ten ve 23:59:59, 31 Aralık 3000, UTC'den önce yse, **_stat32** veya **_wstat32**kullanmadığınız veya **_USE_32BIT_TIME_T**tanımlanmamışsanız, bu durumda tarih yalnızca 23:59:59 Ocak 18, 2038, UTC'ye kadar temsil edilebilir.

## <a name="remarks"></a>Açıklamalar

**_stat** *işlevi, yol* tarafından belirtilen dosya veya dizin hakkında bilgi alır ve *arabellek*tarafından işaret edilen yapıda saklar. **_stat,** çok bayt karakterli dize bağımsız değişkenlerini uygun şekilde işleyerek, şu anda kullanılmakta olan çok bayt kod sayfasına göre çok bayt karakter dizilerini tanıyarak çalışır.

**_wstat** **_stat**geniş karakterli bir versiyonudur; **_wstat** *yol* bağımsız değişkeni geniş karakterli bir dizedir. **_wstat** ve **_stat,** **_wstat** çok bayt karakterli dizeleri işlememesi dışında aynı şekilde çalışır.

Bu işlevlerin varyasyonları 32 veya 64 bit zaman türlerini ve 32 veya 64 bit dosya uzunluklarını destekler. İlk sayısal sonek (**32** veya **64**) kullanılan zaman türünün boyutunu gösterir; ikinci sonek, dosya boyutunun 32 bit veya 64 bit tamsayı olarak temsil edilip edilmediğini belirten **i32** veya **i64'tür.**

**_stat** **_stat64i32**eşdeğerdir ve **strük** **_stat** 64 bitlik bir zaman içerir. **bu, _USE_32BIT_TIME_T** tanımlanmadıkça doğrudur ve bu durumda eski davranış geçerlidir; **_stat** 32 bit, **struct** **_stat** ise 32 bitlik bir zaman içerir. Aynı **_stati64**için de geçerlidir.

> [!NOTE]
> **_wstat** Windows Vista sembolik bağlantıları ile çalışmıyor. Bu gibi durumlarda, **_wstat** her zaman 0 dosya boyutunu bildirir. **_stat** sembolik bağlantılarla doğru şekilde çalışır.

Bu işlev parametrelerini doğrular. *Yol* veya *arabellek* **NULL**ise, geçersiz parametre işleyicisi, [Parametre Doğrulama](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="time-type-and-file-length-type-variations-of-_stat"></a>_stat Zaman Türü ve Dosya Uzunluğu Tür Varyasyonları

|İşlevler|_USE_32BIT_TIME_T tanımlanmış?|Zaman türü|Dosya uzunluğu türü|
|---------------|------------------------------------|---------------|----------------------|
|**_stat**, **_wstat**|Tanımlı değil|64 bit|32 bit|
|**_stat**, **_wstat**|Tanımlanan|32 bit|32 bit|
|**_stat32**, **_wstat32**|Makro tanımından etkilenmez|32 bit|32 bit|
|**_stat64**, **_wstat64**|Makro tanımından etkilenmez|64 bit|64 bit|
|**_stati64**, **_wstati64**|Tanımlı değil|64 bit|64 bit|
|**_stati64**, **_wstati64**|Tanımlanan|32 bit|64 bit|
|**_stat32i64**, **_wstat32i64**|Makro tanımından etkilenmez|32 bit|64 bit|
|**_stat64i32**, **_wstat64i32**|Makro tanımından etkilenmez|64 bit|32 bit|

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstat**|**_stat**|**_stat**|**_wstat**|
|**_tstat64**|**_stat64**|**_stat64**|**_wstat64**|
|**_tstati64**|**_stati64**|**_stati64**|**_wstati64**|
|**_tstat32i64**|**_stat32i64**|**_stat32i64**|**_wstat32i64**|
|**_tstat64i32**|**_stat64i32**|**_stat64i32**|**_wstat64i32**|

SYS\STAT'ta tanımlanan **_stat** yapısı. H, aşağıdaki alanları içerir.

|Alan||
|-|-|
| **st_gid** | Dosyanın sahibi olan grubun sayısal tanımlayıcısı (UNIX'e özgü) Bu alan Windows sistemlerinde her zaman sıfır olacaktır. Yönlendirilen bir dosya Windows dosyası olarak sınıflandırılır. |
| **st_atime** | Dosyaya son erişim zamanı. NTFS'de geçerlidir, ancak FAT biçimlendirilmiş disk sürücülerinde geçerli değildir. |
| **st_ctime** | Dosyanın oluşturulmama zamanı. NTFS'de geçerlidir, ancak FAT biçimlendirilmiş disk sürücülerinde geçerli değildir. |
| **st_dev** | Dosyayı içeren diskin sürücü numarası **(st_rdev**ile aynı). |
| **st_ino** | Dosyaiçin bilgi düğümü **(inode)** sayısı (UNIX'e özgü). UNIX dosya sistemlerinde, **inode** dosya tarih ve saat damgalarını, izinleri ve içeriği açıklar. Dosyalar birbirine sabit bağlandığında, aynı **inode'yi**paylaşırlar. Bu **inode**nedenle **st_ino,** FAT, HPFS veya NTFS dosya sistemlerinde hiçbir anlamı yoktur. |
| **st_mode** | Dosya modu bilgileri için bit maskesi. *Yol* bir dizini belirtse **_S_IFDIR** biti ayarlanır; *yol* sıradan bir dosya veya aygıt belirtse **_S_IFREG** biti ayarlanır. Kullanıcı okuma/yazma bitleri dosyanın izin moduna göre ayarlanır; kullanıcı yürütme bitleri dosya adı uzantısına göre ayarlanır. |
| **st_mtime** | Dosyanın son modifikasyon unun zamanı. |
| **st_nlink** | NTFS olmayan dosya sistemlerinde her zaman 1. |
| **st_rdev** | Dosyayı içeren diskin sürücü numarası **(st_dev**ile aynıdır). |
| **st_size** | Baytlarda dosyanın boyutu; **i64** sonekiile varyasyonlar için 64 bit tamsayı. |
| **st_uid** | Dosyasahibi kullanıcının sayısal tanımlayıcısı (UNIX'e özgü). Bu alan Windows sistemlerinde her zaman sıfır olacaktır. Yönlendirilen bir dosya Windows dosyası olarak sınıflandırılır. |

*Yol* bir aygıta başvuruyorsa, **st_size,** çeşitli zaman alanları, **st_dev**ve **_stat** yapısındaki **st_rdev** alanları anlamsızdır. Çünkü STAT. H, TÜRLER'de tanımlanan [_dev_t](../../c-runtime-library/standard-types.md) türünü kullanır. H, TÜRLER içermelisiniz. STAT'dan önce H. Senin kodunda H.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|
|-------------|---------------------|----------------------|
|**_stat**, **_stat32**, **_stat64**, **_stati64**, **_stat32i64**, **_stat64i32**|\<sys/types.h> \<takip eden sys/stat.h>|\<errno.h>|
|**_wstat**, **_wstat32**, **_wstat64**, **_wstati64**, **_wstat32i64**, **_wstat64i32**|\<sys/types.h> \<ardından sys/stat.h \<> veya wchar.h>|\<errno.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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

[Dosya Işleme](../../c-runtime-library/file-handling.md)<br/>
[_access, _waccess](access-waccess.md)<br/>
[_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_setmbcp](setmbcp.md)<br/>
