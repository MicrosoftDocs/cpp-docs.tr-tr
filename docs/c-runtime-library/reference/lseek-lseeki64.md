---
title: _lseek, _lseeki64
ms.date: 11/04/2016
apiname:
- _lseeki64
- _lseek
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _lseeki64
- _lseek
- lseeki64
helpviewer_keywords:
- lseek function
- _lseek function
- _lseeki64 function
- lseeki64 function
- file pointers [C++], moving
- seek file pointers
ms.assetid: aba8a768-d40e-48c3-b38e-473dbd782f93
ms.openlocfilehash: 4d0320b45cb8cd99f1d9f6494b7dcb17bc545a81
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51326101"
---
# <a name="lseek-lseeki64"></a>_lseek, _lseeki64

Bir dosya işaretçisiyse, belirtilen konuma taşır.

## <a name="syntax"></a>Sözdizimi

```C
long _lseek(
   int fd,
   long offset,
   int origin
);
__int64 _lseeki64(
   int fd,
   __int64 offset,
   int origin
);
```

### <a name="parameters"></a>Parametreler

*FD*<br/>
Açık olan bir dosyaya başvuran dosya tanımlayıcısı.

*uzaklık*<br/>
Bayt sayısı *kaynak*.

*Kaynak*<br/>
Başlangıç konumu.

## <a name="return-value"></a>Dönüş Değeri

**_lseek** dosyanın yeni konumunu başlangıçtan itibaren bayt cinsinden uzaklığı döndürür. **_lseeki64** uzaklığı bir 64-bit tamsayı olarak döndürür. İşlev bir hatayı belirtmek için-1 L döndürür. Hatalı dosya tanımlayıcısı veya değeri gibi geçersiz bir parametre geçirilmiş *kaynak* geçersiz veya tarafından belirtilen konumdaki *uzaklığı* olan dosya başlamadan önce geçersiz parametre işleyicisi olduğu içinde açıklanan şekilde çağırılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütme devam etmesine izin verilirse bu işlevler kümesi **errno** için **EBADF** ve -1 L döndürür. Cihazlarda (terminaller ve yazıcılar gibi) arayan yetersiz, dönüş değeri tanımsızdır.

Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Lseek** işlevi, ilişkili dosya işaretçisini taşır *fd* yeni bir konuma *uzaklığı* bayt *kaynak*. Sonraki işlemi dosya çubuğunda yeni konumda gerçekleşir. *Kaynak* bağımsız değişken Stdio.h içinde tanımlı sabitlerden biri olması gerekir.

|*Kaynak* değeri||
|-|-|
| **SEEK_SET** | Dosyasının başında. |
| **SEEK_CUR** | Dosya işaretçisini geçerli konumu. |
| **SEEK_END** | Dosya sonu. |

Kullanabileceğiniz **_lseek** işaretçi herhangi bir yerde bir dosya veya dosya sonunu yeniden konumlandırmak için.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_lseek**|\<io.h >|
|**_lseeki64**|\<io.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Örnek

```C
// crt_lseek.c
/* This program first opens a file named lseek.txt.
* It then uses _lseek to find the beginning of the file,
* to find the current position in the file, and to find
* the end of the file.
*/

#include <io.h>
#include <fcntl.h>
#include <stdlib.h>
#include <stdio.h>
#include <share.h>

int main( void )
{
   int fh;
   long pos;               /* Position of file pointer */
   char buffer[10];

   _sopen_s( &fh, "crt_lseek.c_input", _O_RDONLY, _SH_DENYNO, 0 );

   /* Seek the beginning of the file: */
   pos = _lseek( fh, 0L, SEEK_SET );
   if( pos == -1L )
      perror( "_lseek to beginning failed" );
   else
      printf( "Position for beginning of file seek = %ld\n", pos );

   /* Move file pointer a little */
    _read( fh, buffer, 10 );

   /* Find current position: */
   pos = _lseek( fh, 0L, SEEK_CUR );
   if( pos == -1L )
      perror( "_lseek to current position failed" );
   else
      printf( "Position for current position seek = %ld\n", pos );

   /* Set the end of the file: */
   pos = _lseek( fh, 0L, SEEK_END );
   if( pos == -1L )
      perror( "_lseek to end failed" );
   else
      printf( "Position for end of file seek = %ld\n", pos );

   _close( fh );
}
```

### <a name="input-crtlseekcinput"></a>Giriş: crt_lseek.c_input

```Input
Line one.
Line two.
Line three.
Line four.
Line five.
```

### <a name="output"></a>Çıkış

```Output
Position for beginning of file seek = 0
Position for current position seek = 10
Position for end of file seek = 57
```

## <a name="see-also"></a>Ayrıca bkz.

[Düşük düzey g/ç](../../c-runtime-library/low-level-i-o.md)<br/>
[fseek, _fseeki64](fseek-fseeki64.md)<br/>
[_tell, _telli64](tell-telli64.md)<br/>
