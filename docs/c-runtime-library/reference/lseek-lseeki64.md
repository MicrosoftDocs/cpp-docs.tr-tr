---
title: _lseek, _lseeki64
ms.date: 4/2/2020
api_name:
- _lseeki64
- _lseek
- _o__lseek
- _o__lseeki64
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
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: d35b3db157d4f33e3a8490c6620a08000ff090f5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341612"
---
# <a name="_lseek-_lseeki64"></a>_lseek, _lseeki64

Dosya işaretçisini belirtilen konuma taşır.

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

*Fd*<br/>
Dosya tanımlayıcısı açık bir dosyaya atıfta.

*Uzaklık*<br/>
*Kaynaktan*bayt sayısı.

*Kökenli*<br/>
İlk pozisyon.

## <a name="return-value"></a>Dönüş Değeri

**_lseek,** dosyanın başlangıcından itibaren yeni konumun ofsetini bayt olarak döndürür. **_lseeki64,** 64 bit'lik bir tamsayıda mahsup sağlar. İşlev bir hatayı belirtmek için -1L döndürür. Hatalı dosya tanımlayıcısı gibi geçersiz bir parametre geçtiyse veya *kaynak* değeri geçersizse veya *ofset* tarafından belirtilen konum dosyanın başlangıcından önceyse, geçersiz parametre işleyicisi [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, bu işlevler **EBADF** ve return -1L **errno** ayarlayın. Arama yapamayan aygıtlarda (terminaller ve yazıcılar gibi), iade değeri tanımsızdır.

Bu ve diğer hata kodları hakkında daha fazla bilgi için [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)bakın.

## <a name="remarks"></a>Açıklamalar

**_lseek** işlevi *fd* ile ilişkili dosya işaretçisini *kaynaktan* *bayt olarak mahsup* edilen yeni bir konuma taşır. Dosyadaki bir sonraki işlem yeni konumda gerçekleşir. *Başlangıç* bağımsız değişkeni, Stdio.h'de tanımlanan aşağıdaki sabitlerden biri olmalıdır.

|*menşe* değeri||
|-|-|
| **SEEK_SET** | Dosyanın başlangıcı. |
| **SEEK_CUR** | Dosya işaretçisinin geçerli konumu. |
| **SEEK_END** | Dosyanın sonu. |

Işaretçiyi bir dosyanın herhangi bir yerinde veya dosyanın sonuna kadar yeniden konumlandırmak için **_lseek** kullanabilirsiniz.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_lseek**|\<io.h>|
|**_lseeki64**|\<io.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="libraries"></a>Kitaplıklar

C çalışma [zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

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

### <a name="input-crt_lseekc_input"></a>Giriş: crt_lseek.c_input

```Input
Line one.
Line two.
Line three.
Line four.
Line five.
```

### <a name="output"></a>Çıktı

```Output
Position for beginning of file seek = 0
Position for current position seek = 10
Position for end of file seek = 57
```

## <a name="see-also"></a>Ayrıca bkz.

[Düşük Seviyeli G/Ç](../../c-runtime-library/low-level-i-o.md)<br/>
[fseek, _fseeki64](fseek-fseeki64.md)<br/>
[_tell, _telli64](tell-telli64.md)<br/>
