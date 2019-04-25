---
title: _locking
ms.date: 11/04/2016
apiname:
- _locking
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
- _locking
helpviewer_keywords:
- locking function
- bytes [C++], locking file
- files [C++], locking bytes
- files [C++], locking
- _locking function
ms.assetid: 099aaac1-d4ca-4827-aed6-24dff9844150
ms.openlocfilehash: 90327ed3388d4f18e0f64f92c33112c9ddd800f5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62157469"
---
# <a name="locking"></a>_locking

Kilitler veya bayt bir dosyanın kilidini açar.

## <a name="syntax"></a>Sözdizimi

```C
int _locking(
   int fd,
   int mode,
   long nbytes
);
```

### <a name="parameters"></a>Parametreler

*FD*<br/>
Dosya tanımlayıcısı.

*Modu*<br/>
Gerçekleştirilecek eylem kilitleniyor.

*nbytes*<br/>
Kilitlemek için bayt sayısı.

## <a name="return-value"></a>Dönüş Değeri

**_locking** başarılı olursa 0 döndürür. Dönüş değeri-1 hata, bu durumda gösteriyor [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) aşağıdaki değerlerden birine ayarlayın.

|errno değeri|Koşul|
|-|-|
| **SPAWN** | (Zaten kilitli veya kilidi dosyası) ihlali kilitleniyor. |
| **EBADF** | Geçersiz dosya tanımlayıcısı. |
| **EDEADLOCK** | Kilit ihlali. Ne zaman iade **_LK_LOCK** veya **_LK_RLCK** bayrağı belirtildi ve 10 denemeden sonra dosya kilitlenemez. |
| **EINVAL** | Geçersiz bağımsız değişken için verilen **_locking**. |

Gibi bir geçersiz dosya tanımlayıcısı hatalı bir parametre nedeniyle başarısız olması durumunda geçersiz parametre işleyicisi açıklandığı gibi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md).

## <a name="remarks"></a>Açıklamalar

**_Locking** işlevi kilitler ya da kilidini açarak *nbytes* tarafından belirtilen dosyanın bayt *fd*. Bir dosyadaki baytları kilitleme erişim için bu baytlardan başka işlemler tarafından engeller. Tüm kilitleme veya kilidini açma dosya işaretçisini geçerli konumunda başlar ve sonraki geçer *nbytes* bayt. Kilit bayt mümkündür dosya sonunu geçti.

*modu* Locking.h içinde tanımlanan aşağıdaki bildirim sabitleri biri olmalıdır.

|*modu* değeri|Efekt|
|-|-|
| **_LK_LOCK** | Belirtilen bayt kilitler. Bayt kilitlenemez, program yeniden 1 saniye sonra hemen çalışır. 10 denemeden sonra bayt kilitlenemez, sabit bir hata döndürür. |
| **_LK_NBLCK** | Belirtilen bayt kilitler. Bayt kilitlenemez, sabit bir hata döndürür. |
| **_LK_NBRLCK** | Aynı **_LK_NBLCK**. |
| **_LK_RLCK** | Aynı **_LK_LOCK**. |
| **_LK_UNLCK** | Önceden kilitlenmiş gerekir belirtilen bayt kilidini açar. |

Bir dosyanın üst üste birden çok bölgede kilitlenebilir. Bir bölge kilidi açılıyor önceden kilitlenmiş gerekir. **_locking** birleştirme bitişik bölgeleri yapar; kilitli iki bölgeleri bitişikse, her bölgede ayrı olarak kilidinin açık olması gerekir. Bölgeler, yalnızca kısa bir süre kilitli olması ve bir dosyayı kapatma veya program çıkmadan önce kilidi.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_locking**|\<io.h > ve \<sys/locking.h >|\<errno.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Örnek

```C
// crt_locking.c
/* This program opens a file with sharing. It locks
* some bytes before reading them, then unlocks them. Note that the
* program works correctly only if the file exists.
*/

#include <sys/types.h>
#include <sys/stat.h>
#include <sys/locking.h>
#include <share.h>
#include <fcntl.h>
#include <stdio.h>
#include <stdlib.h>
#include <io.h>

int main( void )
{
   int  fh, numread;
   char buffer[40];

   /* Quit if can't open file or system doesn't
    * support sharing.
    */
   errno_t err = _sopen_s( &fh, "crt_locking.txt", _O_RDONLY, _SH_DENYNO,
                          _S_IREAD | _S_IWRITE );
   printf( "%d %d\n", err, fh );
   if( err != 0 )
      exit( 1 );

   /* Lock some bytes and read them. Then unlock. */
   if( _locking( fh, LK_NBLCK, 30L ) != -1 )
   {
      long lseek_ret;
      printf( "No one can change these bytes while I'm reading them\n" );
      numread = _read( fh, buffer, 30 );
      buffer[30] = '\0';
      printf( "%d bytes read: %.30s\n", numread, buffer );
      lseek_ret = _lseek( fh, 0L, SEEK_SET );
      _locking( fh, LK_UNLCK, 30L );
      printf( "Now I'm done. Do what you will with them\n" );
   }
   else
      perror( "Locking failed\n" );

   _close( fh );
}
```

### <a name="input-crtlockingtxt"></a>Giriş: crt_locking.txt

```Input
The first thirty bytes of this file will be locked.
```

## <a name="sample-output"></a>Örnek Çıktı

```Output
No one can change these bytes while I'm reading them
30 bytes read: The first thirty bytes of this
Now I'm done. Do what you will with them
```

## <a name="see-also"></a>Ayrıca bkz.

[Dosya İşleme](../../c-runtime-library/file-handling.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
