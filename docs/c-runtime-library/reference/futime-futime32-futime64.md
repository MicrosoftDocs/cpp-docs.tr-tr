---
title: _futime, _futime32, _futime64
ms.date: 4/2/2020
api_name:
- _futime64
- _futime32
- _futime
- _o__futime32
- _o__futime64
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 615e436abf9d763e73d26db61d9063d5e586232b
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82909920"
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

**_Futime** yordamı, *FD*ile ilişkili açık dosyada değişiklik tarihini ve erişim zamanını ayarlar. **_futime** , bağımsız değişkeni bir dosyanın adı veya bir dosyanın yolu yerine açık bir dosyanın dosya tanımlayıcısı olması dışında, [_utime](utime-utime32-utime64-wutime-wutime32-wutime64.md)ile aynıdır. **_Utimbuf** yapısı, yeni değiştirilme tarihi ve erişim saatinin alanlarını içerir. Her iki alan de geçerli değerler içermelidir. **_utimbuf32** ve **_utimbuf64** , sırasıyla 32-bit ve 64 bit zaman türlerinin kullanılması dışında **_utimbuf** benzerdir. **_futime** ve **_utimbuf** 64 bitlik bir zaman türü kullanır ve **_futime64**davranıştaki **_futime** aynıdır. Eski davranışı zorlamaya ihtiyacınız varsa **_USE_32BIT_TIME_T**tanımlayın. Bunun yapılması, **_futime32** davranıştaki **_futime** aynı olmasına neden olur ve **_utimbuf** yapısının 32 bit zaman türünü kullanmasına neden olur ve bu da **__utimbuf32**eşdeğerini yapar.

**__utimbuf64** yapısını kullanan **_futime64**dosya tarihlerini 23:59:59, 31 Aralık 3000, UTC; ile okuyabilir ve değiştirebilir **_futime32** çağrısı, dosyadaki tarihin 18 Ocak 2038, UTC 23:59:59 ' den sonra olması durumunda başarısız olur. Gece yarısı, 1 Ocak 1970, bu işlevlerin tarih aralığının alt sınırdır.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|İsteğe bağlı başlık|
|--------------|---------------------|---------------------|
|**_futime**|\<sys/utime. h>|\<errno. h>|
|**_futime32**|\<sys/utime. h>|\<errno. h>|
|**_futime64**|\<sys/utime. h>|\<errno. h>|

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
