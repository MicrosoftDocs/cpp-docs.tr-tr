---
title: _chsize | Microsoft Docs
ms.custom: ''
ms.date: 03/29/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- size
- _chsize function
- size, changing file
- files [C++], changing size
- chsize function
ms.assetid: b3e881c5-7b27-4837-a3d4-c51591ab10ff
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eb40d218439ebe308e7d7cf01ab5043a2ebb3b1e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32395760"
---
# <a name="chsize"></a>_chsize

Dosyasının boyutu değişir. Daha güvenli bir sürümünü kullanılabilir; bkz: [_chsize_s](chsize-s.md).

## <a name="syntax"></a>Sözdizimi

```C
int _chsize(
   int fd,
   long size
);
```

### <a name="parameters"></a>Parametreler

*FD*<br/>
Açık olan bir dosyaya başvuruda bulunan dosya tanımlayıcısı.

*Boyutu*<br/>
Yeni dosyanın bayt cinsinden uzunluğu.

## <a name="return-value"></a>Dönüş Değeri

**_chsize** dosya boyutu başarıyla değiştirilirse 0 değerini döndürür. Dönüş değeri -1, bir hata gösterir: **errno** ayarlanır **EACCES** belirtilen dosya salt okunur ise veya belirtilen dosya için erişime karşı kilitlenmiş **EBADF** varsa tanımlayıcısı geçersiz **ENOSPC** boşluk cihazda bırakılırsa veya **EINVAL** varsa *boyutu* sıfırdan küçüktür.

Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu ve diğer hakkında daha fazla bilgi için dönüş kodları.

## <a name="remarks"></a>Açıklamalar

**_Chsize** işlevi genişletir veya ilişkili dosya kesen *fd* tarafından belirtilen uzunluğa *boyutu*. Dosya yazma izin veren bir modda açık olması gerekir. Boş karakterler ('\0') dosya genişletilmişse eklenir. Dosya kesilirse, dosyanın özgün uzunluğu kısaltılmış dosyasının sonuna tüm veriler kaybolur.

Bu işlev parametrelerini doğrular. Varsa *boyutu* sıfırdan küçüktür veya *fd* hatalı dosya tanımlayıcısı açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|
|-------------|---------------------|---------------------|
|**_chsize**|\<io.h >|\<errno.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
