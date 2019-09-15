---
title: _futime, _futime32, _futime64
ms.date: 11/04/2016
api_name:
- _futime64
- _futime32
- _futime
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
- api-ms-win-crt-time-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- futime
- _futime
- futime64
- _futime64
helpviewer_keywords:
- _futime function
- futime32 function
- futime64 function
- file modification time [C++]
- _futime64 function
- futime function
- _futime32 function
ms.assetid: b942ce8f-5cc7-4fa8-ab47-de5965eded53
ms.openlocfilehash: 3de638f08882e2aae4743311730afcd888c43a60
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70956227"
---
# <a name="_futime-_futime32-_futime64"></a>_futime, _futime32, _futime64

Açık bir dosyada değişiklik saatini ayarlar.

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
Açık dosyaya dosya tanımlayıcısı.

*FILETIME*<br/>
Yeni değiştirilme tarihini içeren yapıya yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa 0 döndürün. Bir hata oluşursa, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, işlev-1 döndürür ve **errno** , **EBADF**olarak ayarlanır; geçersiz bir dosya tanımlayıcısı veya **EINVAL**, geçersiz bir parametre belirtir.

## <a name="remarks"></a>Açıklamalar

**_Fütime** yordamı, *FD*ile ilişkili açık dosyada değişiklik tarihini ve erişim zamanını ayarlar. **_futime** , bağımsız değişkeni bir dosyanın adı veya bir dosyanın yolu yerine açık bir dosyanın dosya tanımlayıcısı olması dışında, [_utime](utime-utime32-utime64-wutime-wutime32-wutime64.md)ile aynıdır. **_Utimara** yapısı, yeni değiştirilme tarihi ve erişim saatinin alanlarını içerir. Her iki alan de geçerli değerler içermelidir. **_utimbuf32** ve **_utimbuf64** , sırasıyla 32-bit ve 64 bit zaman türlerinin kullanılması dışında **_utimarabelleğe** benzer. **_futime** ve **_utimarabelleğe** 64 bitlik bir zaman türü kullanın ve **_fütime** , davranışta **_futime64**ile aynıdır. Eski davranışı zorlamaya ihtiyacınız varsa **_Use_32bit_time_t**tanımlayın. Bu durum, **_futime32** ' de davranışta aynı olmasına neden olur ve **_utimlik** yapısının 32 bit zaman türünü kullanmasına neden olur ve bu da **__utimbuf32**ile eşdeğer hale gelir.

**__utimbuf64** yapısını kullanan **_futime64**, dosya tarihlerini 23:59:59, 31 Aralık 3000, UTC; ile okuyabilir ve değiştirebilir Bu durumda, dosyadaki tarihin 18 Ocak 2038, UTC 23:59:59 'den daha sonra olması durumunda **_futime32** çağrısı başarısız olur. Gece yarısı, 1 Ocak 1970, bu işlevlerin tarih aralığının alt sınırdır.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|İsteğe bağlı başlık|
|--------------|---------------------|---------------------|
|**_fusaati**|\<sys/utime. h >|\<errno. h >|
|**_futime32**|\<sys/utime. h >|\<errno. h >|
|**_futime64**|\<sys/utime. h >|\<errno. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

### <a name="input-crt_futimec_input"></a>Giriş: crt_futime. c_input

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
