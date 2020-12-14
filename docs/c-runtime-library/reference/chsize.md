---
description: 'Hakkında daha fazla bilgi edinin: _chsize'
title: _chsize
ms.date: 4/2/2020
api_name:
- _chsize
- _o__chsize
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _chsize
helpviewer_keywords:
- size
- _chsize function
- size, changing file
- files [C++], changing size
- chsize function
ms.assetid: b3e881c5-7b27-4837-a3d4-c51591ab10ff
ms.openlocfilehash: 16a65c145e33a0fbafcc9d0f2b0fed3b9f2b516f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97274898"
---
# <a name="_chsize"></a>_chsize

Bir dosyanın boyutunu değiştirir. Daha güvenli bir sürüm kullanılabilir; bkz. [_chsize_s](chsize-s.md).

## <a name="syntax"></a>Sözdizimi

```C
int _chsize(
   int fd,
   long size
);
```

### <a name="parameters"></a>Parametreler

*FD*<br/>
Açık bir dosyaya başvuran dosya tanımlayıcısı.

*boyutla*<br/>
Dosyanın bayt cinsinden yeni uzunluğu.

## <a name="return-value"></a>Dönüş Değeri

**_chsize** , dosya boyutu başarıyla değiştirilmişse 0 değerini döndürür. -1 ' in dönüş değeri bir hatayı **gösterir: belirtilen** dosya salt okunurdur veya belirtilen dosya **Access 'e karşı** kilitliyse, tanımlayıcı geçersizse, cihazda boş alan yoksa **enospc** , veya *Boyut* sıfırdan küçükse, **EINVAL** **olarak ayarlanmalıdır** .

Bu ve diğer dönüş kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) .

## <a name="remarks"></a>Açıklamalar

**_Chsize** işlevi *FD* ile ilişkili dosyayı *boyutuna* göre belirtilen uzunluğa genişletir veya keser. Dosyanın yazmaya izin veren bir modda açık olması gerekir. Dosya genişletilmişse null karakterler (' \ 0 ') eklenir. Dosya kesilmişse, kısaltılmış dosyanın sonundaki tüm veriler dosyanın özgün uzunluğuna kaybedilir.

Bu işlev, parametrelerini doğrular. *Boyut* sıfırdan küçükse veya *FD* hatalı bir dosya Tanımlayıcıdaysa, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_chsize**|\<io.h>|\<errno.h>|

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
