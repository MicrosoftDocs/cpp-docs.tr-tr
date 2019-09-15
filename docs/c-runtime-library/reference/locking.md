---
title: _locking
ms.date: 11/04/2016
api_name:
- _locking
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _locking
helpviewer_keywords:
- locking function
- bytes [C++], locking file
- files [C++], locking bytes
- files [C++], locking
- _locking function
ms.assetid: 099aaac1-d4ca-4827-aed6-24dff9844150
ms.openlocfilehash: 4450c511b9d98c31b7e6a777f54f3bd8e0affbb7
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70953263"
---
# <a name="_locking"></a>_locking

Bir dosyanın baytlarını kilitler veya kilitlerini kaldırır.

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

*modundaysa*<br/>
Gerçekleştirilecek kilit eylemi.

*nBytes*<br/>
Kilitlenecek bayt sayısı.

## <a name="return-value"></a>Dönüş Değeri

**_kilitleme** başarılı olursa 0 döndürür. -1 ' in dönüş değeri hatayı gösterir, bu durumda [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) aşağıdaki değerlerden birine ayarlanır.

|errno değeri|Koşul|
|-|-|
| **EACCES** | Kilitleme ihlali (dosya zaten kilitli veya kilidi açılmış). |
| **EBADF** | Geçersiz dosya tanımlayıcısı. |
| **EDEADLOCK** | Kilitleme ihlali. **_LK_LOCK** veya **_LK_RLCK** bayrağı belirtildiğinde ve 10 denemeden sonra dosya kilitlenemediğinde döndürülür. |
| **EINVAL** | **_Kilitleme**için geçersiz bir bağımsız değişken verildi. |

Hata, geçersiz bir dosya tanımlayıcısı gibi hatalı bir parametre nedeniyle kaynaklanıyorsa, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır.

## <a name="remarks"></a>Açıklamalar

**_Lock** işlevi *FD*tarafından belirtilen dosyanın *nBytes* baytını kilitler veya kilidini açar. Bir dosyadaki kilitleme baytları diğer işlemlere göre bu baytlara erişimi engeller. Tüm kilitleme veya kilit açma işlemi, dosya işaretçisinin geçerli konumunda başlar ve sonraki *nBayt* baytları için devam eder. Dosya sonunun ötesinde baytları kilitlemek mümkündür.

*mod* , kilitleme. h içinde tanımlanan aşağıdaki bildirim sabitlerinden biri olmalıdır.

|*mod* değeri|Efekt|
|-|-|
| **_LK_LOCK** | Belirtilen baytları kilitler. Baytlar kilitlenmediyse, program 1 saniye sonra hemen yeniden dener. 10 denemeden sonra baytlar kilitlenmediyse, sabit bir hata döndürür. |
| **_LK_NBLCK** | Belirtilen baytları kilitler. Baytlar kilitlenmediyse, sabit bir hata döndürür. |
| **_LK_NBRLCK** | **_LK_NBLCK**ile aynı. |
| **_LK_RLCK** | **_LK_LOCK**ile aynı. |
| **_LK_UNLCK** | Daha önce kilitli olması gereken belirtilen baytların kilidini açar. |

Bir dosyanın örtüşmeyen birden çok bölgesi kilitlenebilir. Kilitlenmiş bir bölgenin daha önce kilitli olması gerekir. **_kilitleme** bitişik bölgeleri birleştirmez; iki kilitli bölge bitişik ise, her bölgenin ayrı ayrı açılması gerekir. Bölgeler yalnızca kısa bir süre kilitli olmalıdır ve bir dosyayı kapatmadan veya programdan çıkmadan önce kilidinin açılması gerekir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_locking**|\<GÇ. h > ve \<sys/kilitleme. h >|\<errno. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

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

### <a name="input-crt_lockingtxt"></a>Giriş: crt_locking. txt

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
