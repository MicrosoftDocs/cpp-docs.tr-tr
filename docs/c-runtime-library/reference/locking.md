---
title: _locking
ms.date: 4/2/2020
api_name:
- _locking
- _o__locking
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
- _locking
helpviewer_keywords:
- locking function
- bytes [C++], locking file
- files [C++], locking bytes
- files [C++], locking
- _locking function
ms.assetid: 099aaac1-d4ca-4827-aed6-24dff9844150
ms.openlocfilehash: 2c6ee763a1491a744b25cbb517886e9354ca6152
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81342054"
---
# <a name="_locking"></a>_locking

Bir dosyanın baytlarını kilitler veya açar.

## <a name="syntax"></a>Sözdizimi

```C
int _locking(
   int fd,
   int mode,
   long nbytes
);
```

### <a name="parameters"></a>Parametreler

*Fd*<br/>
Dosya tanımlayıcısı.

*Modu*<br/>
Gerçekleştirmek için eylemi kilitleme.

*nbayt*<br/>
Kilitlenebilen bayt sayısı.

## <a name="return-value"></a>Dönüş Değeri

**_locking** başarılı olursa 0 döndürür. -1'in geri dönüş değeri, hatayı gösterir ve bu durumda [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) aşağıdaki değerlerden birine ayarlanır.

|errno değeri|Koşul|
|-|-|
| **EACCES** | Kilitleme ihlali (dosya zaten kilitli veya kilidi açık). |
| **Ebadf** | Geçersiz dosya tanımlayıcısı. |
| **EDEADLOCK** | Kilitleme ihlali. **_LK_LOCK** veya **_LK_RLCK** bayrağı belirtildiğinde döndürülür ve dosya 10 denemeden sonra kilitlenemez. |
| **Eınval** | Geçersiz bir argüman **_locking**verildi. |

Hata, geçersiz bir dosya tanımlayıcısı gibi hatalı bir parametreden kaynaklanıyorsa, geçersiz parametre işleyicisi [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır.

## <a name="remarks"></a>Açıklamalar

**_locking** işlevi *fd*tarafından belirtilen dosyanın *nbytebaytlarını* kilitler veya açar. Bir dosyadaki baytların kilitlenerek diğer işlemler tarafından bu baytlara erişimi engeller. Tüm kilitleme veya kilidini açma dosya işaretçisinin geçerli konumunda başlar ve sonraki *nbytes* baytları için ilerler. Dosyanın son ucuna bayt kilitlemek mümkündür.

*modu,* Locking.h'de tanımlanan aşağıdaki bildirim sabitlerinden biri olmalıdır.

|*mod* değeri|Etki|
|-|-|
| **_LK_LOCK** | Belirtilen baytları kilitler. Baytlar kilitlenemezse, program 1 saniye sonra hemen tekrar çalışır. 10 denemeden sonra baytlar kilitlenemezse, sabit bir hata döndürür. |
| **_LK_NBLCK** | Belirtilen baytları kilitler. Baytlar kilitlenemezse, sabit bir hata döndürür. |
| **_LK_NBRLCK** | **_LK_NBLCK**gibi. |
| **_LK_RLCK** | **_LK_LOCK**gibi. |
| **_LK_UNLCK** | Daha önce kilitlenmiş olması gereken belirtilen baytların kilidini açar. |

Bir dosyanın çakışmayan birden çok bölgesi kilitlenebilir. Kilidi açılan bir bölge daha önce kilitlenmiş olmalıdır. **_locking** komşu bölgeleri birleştirmez; iki kilitli bölge bitişikse, her bölgenin ayrı olarak kilidi açılmalıdır. Bölgeler yalnızca kısa bir süre kilitlenmeli ve bir dosyayı kapatmadan veya programdan çıkmadan önce kilidi açılmalıdır.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|
|-------------|---------------------|---------------------|
|**_locking**|\<io.h> \<ve sys/locking.h>|\<errno.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="libraries"></a>Kitaplıklar

C çalışma [zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

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

### <a name="input-crt_lockingtxt"></a>Giriş: crt_locking.txt

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

[Dosya Işleme](../../c-runtime-library/file-handling.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
