---
title: _chsize
ms.date: 03/29/2018
apiname:
- _chsize
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
- _chsize
helpviewer_keywords:
- size
- _chsize function
- size, changing file
- files [C++], changing size
- chsize function
ms.assetid: b3e881c5-7b27-4837-a3d4-c51591ab10ff
ms.openlocfilehash: 5c60f3aa08a405eb9a83dc6ba8636cd316a32925
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62340332"
---
# <a name="chsize"></a>_chsize

Bir dosyanın boyutunu değiştirir. Daha güvenli bir sürümü kullanılabilir; bkz: [_chsize_s](chsize-s.md).

## <a name="syntax"></a>Sözdizimi

```C
int _chsize(
   int fd,
   long size
);
```

### <a name="parameters"></a>Parametreler

*FD*<br/>
Açık olan bir dosyaya başvuran dosya tanımlayıcısı.

*Boyutu*<br/>
Yeni dosyanın bayt cinsinden uzunluğu.

## <a name="return-value"></a>Dönüş Değeri

**_chsize** dosya boyutu başarıyla değiştirilirse, 0 değerini döndürür. Hata-1 değeri belirtir: **errno** ayarlanır **SPAWN** belirtilen dosya salt okunur veya belirtilen dosya için erişim karşı kilitli **EBADF** varsa tanımlayıcı geçersiz **ENOSPC** boşluk cihazda bırakılırsa veya **EINVAL** varsa *boyutu* sıfırdan küçüktür.

Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu ve diğer hakkında daha fazla bilgi için dönüş kodları.

## <a name="remarks"></a>Açıklamalar

**_Chsize** işlevini genişletir veya ilişkili dosya keser *fd* tarafından belirtilen uzunluktan *boyutu*. Dosya yazma izin veren bir modda açık olmalıdır. Dosya uzatıldıysa null karakterleri ('\0') eklenir. Dosya kesilmiş, özgün dosya uzunluğu kısaltılmış dosyanın sonundan tüm veriler kaybolur.

Bu işlev, parametrelerini doğrular. Varsa *boyutu* sıfırdan küçük veya *fd* bir hatalı dosya tanımlayıcısı açıklandığı gibi geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_chsize**|\<io.h >|\<errno.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_chsize.c
// This program uses _filelength to report the size
// of a file before and after modifying it with _chsize.

#include <io.h>
#include <fcntl.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <stdio.h>
#include <share.h>

int main( void )
{
   int fh, result;
   unsigned int nbytes = BUFSIZ;

   // Open a file
   if( _sopen_s( &fh, "data", _O_RDWR | _O_CREAT, _SH_DENYNO,
                 _S_IREAD | _S_IWRITE ) == 0 )
   {
      printf( "File length before: %ld\n", _filelength( fh ) );
      if( ( result = _chsize( fh, 329678 ) ) == 0 )
         printf( "Size successfully changed\n" );
      else
         printf( "Problem in changing the size\n" );
      printf( "File length after:  %ld\n", _filelength( fh ) );
      _close( fh );
   }
}
```

```Output
File length before: 0
Size successfully changed
File length after:  329678
```

## <a name="see-also"></a>Ayrıca bkz.

[Dosya İşleme](../../c-runtime-library/file-handling.md)<br/>
[_close](close.md)<br/>
[_sopen, _wsopen](sopen-wsopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
