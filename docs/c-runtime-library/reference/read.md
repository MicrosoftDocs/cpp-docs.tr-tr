---
title: _read
ms.date: 11/04/2016
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
ms.openlocfilehash: 8c43cbbc2681433bda02038ae73a827fad904835
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50658451"
---
# <a name="read"></a>_read

Bir dosyadan verileri okur.

## <a name="syntax"></a>Sözdizimi

```C
int _read(
   int fd,
   void *buffer,
   unsigned int count
);
```

### <a name="parameters"></a>Parametreler

*FD*<br/>
Açık dosyaya başvuran dosya tanımlayıcısı.

*Arabellek*<br/>
Veri için depolama konumu.

*Sayısı*<br/>
En fazla bayt sayısı.

## <a name="return-value"></a>Dönüş Değeri

**_read** , küçük olabilir, okunan bayt sayısını döndürür daha *sayısı* değerinden daha az *sayısı* bayt sol dosyasında veya dosyanın metin modunda açıldıysa, her bir satır başı durumda başı satır besleme çifti '\r\n' bir '\n' tek satır besleme karakteri ile değiştirilir. Yalnızca tek bir satır besleme karakteri, dönüş değeri olarak sayılır. Değiştirilen dosya işaretçisini etkilemez.

İşlev dosya sonunda okumaya çalışır, 0 döndürür. Varsa *fd* olduğundan geçerli değil, dosya okuma için açık değil veya dosyanın kilitli, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Devam etmek için işlev -1 döndürür ve kümeleri yürütülmesine izin veriliyorsa **errno** için **EBADF**.

Varsa *arabellek* olduğu **NULL**, geçersiz parametre işleyicisi çağrılır. Yürütme devam etmesine izin verilirse işlev -1 döndürür ve **errno** ayarlanır **EINVAL**.

Bu ve diğer dönüş kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Read** işlevi, en fazla okur *sayısı* baytlara *arabellek* ilişkili dosyasından *fd*. Belirtilen dosya ile ilişkili dosya işaretçisi konumunu okuma işlemi başlar. Sonra okuma işlemi, dosya işaretçisini okunmamış sonraki karaktere işaret eder.

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
   int fh;
   unsigned int nbytes = 60000, bytesread;

   /* Open file for input: */
   if( _sopen_s( &fh, "crt_read.txt", _O_RDONLY, _SH_DENYNO, 0 ) )
   {
      perror( "open failed on input file" );
      exit( 1 );
   }

   /* Read in input: */
   if( ( bytesread = _read( fh, buffer, nbytes ) ) <= 0 )
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
