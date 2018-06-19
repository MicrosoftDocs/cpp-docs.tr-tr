---
title: _futime, _futime32, _futime64 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _futime64
- _futime32
- _futime
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
- futime
- _futime
- futime64
- _futime64
dev_langs:
- C++
helpviewer_keywords:
- _futime function
- futime32 function
- futime64 function
- file modification time [C++]
- _futime64 function
- futime function
- _futime32 function
ms.assetid: b942ce8f-5cc7-4fa8-ab47-de5965eded53
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 864bba5b88c7e52b55bd86a61edaaac2d22b0346
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32402315"
---
# <a name="futime-futime32-futime64"></a>_futime, _futime32, _futime64

Açık bir dosyada değişiklik zamanı ayarlar.

## <a name="syntax"></a>Sözdizimi

```C
int _futime(
   int fd,
   struct _utimbuf *filetime
);
int _futime32(
   int fd,
   struct __utimbuf32 *filetime
);
int _futime64(
   int fd,
   struct __utimbuf64 *filetime
);
```

### <a name="parameters"></a>Parametreler

*FD*<br/>
Açık dosyasına dosya tanımlayıcısı.

*fıletıme*<br/>
Yeni değişiklik tarihi içeren yapısına yönelik işaretçinin.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa 0 döndürür. Bir hata oluşursa, geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, işlevi -1 döndürür ve **errno** ayarlanır **EBADF**, geçersiz dosya açıklayıcısı belirten veya **EINVAL**, geçersiz bir belirten parametre.

## <a name="remarks"></a>Açıklamalar

**_Futime** ilişkili açık dosyada yordamı ayarlar değiştirme tarihi ve erişim zamanı *fd*. **_futime** aynıdır [_utime](utime-utime32-utime64-wutime-wutime32-wutime64.md), açık bir dosyanın dosya tanımlayıcısı yerine, bir dosya veya bir dosya için bir yol adı bağımsız değişkeni olması dışında. **_Utimbuf** yapısı yeni değiştirilme tarihi ve erişim saat için alanlar içeriyor. Her iki alan geçerli değerler içermelidir. **_utimbuf32** ve **_utimbuf64** özdeş **_utimbuf** dışındaki 32-bit ve 64-bit saat türleri kullanım için sırasıyla. **_futime** ve **_utimbuf** bir 64-bit time türü kullanın ve **_futime** için davranış aynıdır **_futime64**. Eski davranışı zorlamak gerekiyorsa, tanımlamak **_USE_32BIT_TIME_T**. Bu neden olur. Bunu yapmak **_futime** davranışı için aynı olacak şekilde **_futime32** ve neden **_utimbuf** içineşdeğeryapmadan32-bitsüretürünükullanmakiçinyapısı **__utimbuf32**.

**_futime64**, kullanan **__utimbuf64** yapısı okuyabilir ve dosya tarihleri ile 23:59:59, 31 Aralık 3000 UTC; ancak değişiklik yapılan bir çağrı **_futime32** dosya tarihteki başarısız olur Daha fazla 23:59:59 18 Ocak 2038, UTC. Gece yarısından, 1 Ocak 1970'ten, bu işlevler için tarih aralığını alt sınırdır.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|İsteğe bağlı üstbilgi|
|--------------|---------------------|---------------------|
|**_futime**|\<sys/utime.h >|\<errno.h >|
|**_futime32**|\<sys/utime.h >|\<errno.h >|
|**_futime64**|\<sys/utime.h >|\<errno.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_futime.c
// This program uses _futime to set the
// file-modification time to the current time.

#include <stdio.h>
#include <stdlib.h>
#include <fcntl.h>
#include <io.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <sys/utime.h>
#include <share.h>

int main( void )
{
   int hFile;

   // Show file time before and after.
   system( "dir crt_futime.c_input" );

   _sopen_s( &hFile, "crt_futime.c_input", _O_RDWR, _SH_DENYNO, 0 );

   if( _futime( hFile, NULL ) == -1 )
      perror( "_futime failed\n" );
   else
      printf( "File time modified\n" );

   _close (hFile);

   system( "dir crt_futime.c_input" );
}
```

### <a name="input-crtfutimecinput"></a>Giriş: crt_futime.c_input

```Input
Arbitrary file contents.
```

### <a name="sample-output"></a>Örnek Çıktı

```Output
 Volume in drive Z has no label.
 Volume Serial Number is 5C68-57C1

 Directory of Z:\crt

 03/25/2004  10:40 AM                24 crt_futime.c_input
               1 File(s)             24 bytes
               0 Dir(s)  24,268,476,416 bytes free
 Volume in drive Z has no label.
 Volume Serial Number is 5C68-57C1

 Directory of Z:\crt

 03/25/2004  10:41 AM                24 crt_futime.c_input
               1 File(s)             24 bytes
               0 Dir(s)  24,268,476,416 bytes free
File time modified
```

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Yönetimi](../../c-runtime-library/time-management.md)<br/>
