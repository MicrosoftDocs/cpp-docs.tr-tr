---
title: _utime, _utime32, _utime64, _wutime, _wutime32, _wutime64 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _utime64
- _utime
- _wutime
- _wutime64
- _wutime32
- _utime32
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
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cd8737d6391ea1effd50e967008520b2d77707e6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32417717"
---
# <a name="utime-utime32-utime64-wutime-wutime32-wutime64"></a>_utime, _utime32, _utime64, _wutime, _wutime32, _wutime64

Dosya değişikliği zamanı ayarlayın.

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

*Dosya adı*<br/>
Yol veya dosya adı içeren bir dize işaretçi.

*Saatleri*<br/>
İşaretçi saat değerleri depolanır.

## <a name="return-value"></a>Dönüş Değeri

Dosya değişikliği zamanı değişirse bu işlevlerin her biri 0 döndürür. Dönüş değeri-1 hata gösterir. Geçersiz bir parametre verilmezse, geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler -1 döndürür ve **errno** aşağıdaki değerlerden birine ayarlayın:

|errno değeri|Koşul|
|-|-|
**EACCES**|Dizin veya salt okunur dosya yolunu belirtir
**EINVAL**|Geçersiz *kez* bağımsız değişken
**EMFILE**|Çok fazla açık dosya (dosya değiştirme saati değiştirmek için açık olması gerekir)
**ENOENT**|Yol veya dosya adı bulunamadı

Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu ve diğer hakkında daha fazla bilgi için dönüş kodları.

Değişiklik tarihi yarısından, 1 Ocak 1970 ve kullanılan işlev bitiş tarihinden önce ise, bir dosya için tarih değiştirilebilir. **_utime** ve **_wutime** 23:59:59, 31 Aralık 3000 UTC bitiş tarihi olacak şekilde bir 64-bit saat değeri kullanın. Varsa **_USE_32BIT_TIME_T** tanımlanan eski davranışı zorlamak için bitiş tarihi 23:59:59 18 Ocak 2038, UTC değil. **_utime32** veya **_wutime32** 32-bit zamanı tür bağımsız olarak mı kullanmak **_USE_32BIT_TIME_T** tanımlanmış ve her zaman önceki bir son tarihe sahip. **_utime64** veya **_wutime64** bu işlevlerin her zaman daha sonra bitiş tarihini destekleyecek biçimde 64-bit zamanı tür her zaman kullanın.

## <a name="remarks"></a>Açıklamalar

**_Utime** işlevi tarafından belirtilen dosyayı değiştirme saati ayarlar *filename **.* İşlem Saati değiştirmek için dosyaya yazma erişimi olmalıdır. Windows işletim sisteminde, erişim zamanı ve değiştirme saati değiştirebilirsiniz **_utimbuf** yapısı. Varsa *kez* olan bir **NULL** işaretçisi değiştirme saati geçerli yerel saat olarak ayarlanır. Aksi takdirde, *kez* türü yapısına işaret etmelidir **_utimbuf**, SYS\UTIME içinde tanımlı. H.

**_Utimbuf** yapısı depolar tarafından kullanılan dosya erişim ve değişiklik sürelerinin **_utime** dosya değişikliği tarihleri değiştirmek için. Türü her ikisi de aşağıdaki alanları yapısının **time_t**:

|Alan||
|-|-|
**actime**|Dosya erişimi süresi
**modtime**|Dosya değişikliği zamanı

Belirli sürümlerini **_utimbuf** yapısı (**_utimebuf32** ve **__utimbuf64**) zamanı tür 32-bit ve 64 bit sürümleri kullanılarak tanımlanır. Bunlar, 32 bit ve 64-bit belirli sürümlerinde bu işlevi kullanılır. **_utimbuf** kendisini varsayılan sürece bir 64-bit süre türünü kullanan **_USE_32BIT_TIME_T** tanımlanır.

**_utime** aynıdır **_futime** dışında *filename* bağımsız değişkeni **_utime** bir dosya adı veya bir dosya tanımlayıcısı yerine bir dosya yolu bir dosyasını açın.

**_wutime** bir joker karakter sürümü **_utime**; *filename* bağımsız değişkeni **_wutime** bir joker karakter dizesidir. Bu işlevler aynı şekilde aksi davranır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tutime**|**_utime**|**_utime**|**_wutime**|
|**_tutime32**|**_utime32**|**_utime32**|**_wutime32**|
|**_tutime64**|**_utime64**|**_utime64**|**_wutime64**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli üst bilgileri|İsteğe bağlı üstbilgi|
|-------------|----------------------|----------------------|
|**_utime**, **_utime32**, **_utime64**|\<sys/utime.h >|\<errno.h >|
|**_utime64**|\<sys/utime.h >|\<errno.h >|
|**_wutime**|\<utime.h > veya \<wchar.h >|\<errno.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Bu programın kullandığı **_utime** dosya değişikliği zamanı geçerli saati ayarlamak için.

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
[_stat, _wstat işlevleri](stat-functions.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
