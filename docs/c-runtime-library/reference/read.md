---
title: _read
ms.date: 02/13/2019
apiname:
- _read
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
- _read
helpviewer_keywords:
- data [CRT]
- _read function
- read function
- data [C++], reading
- reading data [C++]
- files [C++], reading
ms.assetid: 2ce9c433-57ad-47fe-9ac1-4a7d4c883d30
ms.openlocfilehash: 40f52ea37ae5419fe986aa505aad4fddfe8403ff
ms.sourcegitcommit: eb2b34a24e6edafb727e87b138499fa8945f981e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2019
ms.locfileid: "56264796"
---
# <a name="read"></a>_read

Bir dosyadan verileri okur.

## <a name="syntax"></a>Sözdizimi

```C
int _read(
   int const fd,
   void * const buffer,
   unsigned const buffer_size
);
```

### <a name="parameters"></a>Parametreler

*FD*<br/>
Açık dosyaya başvuran dosya tanımlayıcısı.

*Arabellek*<br/>
Veri için depolama konumu.

*buffer_size*<br/>
Okunacak bayt sayısı.

## <a name="return-value"></a>Dönüş Değeri

**_read** , küçük olabilir, okunan bayt sayısını döndürür daha *buffer_size* değerinden daha az *buffer_size* bayt sol dosyasında veya dosyanın metin modunda açıldıysa. Metin modunda çifti her satır başı satır besleme `\r\n` tek satır besleme karakteri ile değiştirilir `\n`. Yalnızca tek bir satır besleme karakteri, dönüş değeri olarak sayılır. Değiştirilen dosya işaretçisini etkilemez.

İşlev dosya sonunda okumaya çalışır, 0 döndürür. Varsa *fd* olduğundan geçerli değil, dosyanın okunması için açık olmadığından veya dosyanın kilitli, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Devam etmek için işlev -1 döndürür ve kümeleri yürütülmesine izin veriliyorsa **errno** için **EBADF**.

Varsa *arabellek* olduğu **NULL**, veya *buffer_size* > **INT_MAX**, geçersiz parametre işleyicisi çağrılır. Yürütme devam etmesine izin verilirse işlev -1 döndürür ve **errno** ayarlanır **EINVAL**.

Bu ve diğer dönüş kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Read** işlevi, en fazla okur *buffer_size* baytlara *arabellek* ilişkili dosyasından *fd*. Belirtilen dosya ile ilişkili dosya işaretçisi konumunu okuma işlemi başlar. Sonra okuma işlemi, dosya işaretçisini okunmamış sonraki karaktere işaret eder.

Dosyayı metin modunda açıldıysa, salt okunur olduğunda sonlandırır **_read** bir dosya sonu göstergesi olarak kabul edilir bir CTRL + Z karakterini karşılaşır. Kullanım [_lseek](lseek-lseeki64.md) dosya sonu göstergesi temizleyin.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_read**|\<io.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Örnek

```C
// crt_read.c
/* This program opens a file named crt_read.txt
* and tries to read 60,000 bytes from
* that file using _read. It then displays the
* actual number of bytes read.
*/

#include <fcntl.h>      /* Needed only for _O_RDWR definition */
#include <io.h>
#include <stdlib.h>
#include <stdio.h>
#include <share.h>

char buffer[60000];

int main( void )
{
   int fh, bytesread;
   unsigned int nbytes = 60000;

   /* Open file for input: */
   if ( _sopen_s( &fh, "crt_read.txt", _O_RDONLY, _SH_DENYNO, 0 ))
   {
      perror( "open failed on input file" );
      exit( 1 );
   }

   /* Read in input: */
   if (( bytesread = _read( fh, buffer, nbytes )) <= 0 )
      perror( "Problem reading file" );
   else
      printf( "Read %u bytes from file\n", bytesread );

   _close( fh );
}
```

### <a name="input-crtreadtxt"></a>Giriş: crt_read.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>Çıkış

```Output
Read 19 bytes from file
```

## <a name="see-also"></a>Ayrıca bkz.

[Düşük düzey g/ç](../../c-runtime-library/low-level-i-o.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[fread](fread.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_write](write.md)<br/>
