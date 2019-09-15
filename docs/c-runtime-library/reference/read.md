---
title: _read
ms.date: 02/13/2019
api_name:
- _read
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
- _read
helpviewer_keywords:
- data [CRT]
- _read function
- read function
- data [C++], reading
- reading data [C++]
- files [C++], reading
ms.assetid: 2ce9c433-57ad-47fe-9ac1-4a7d4c883d30
ms.openlocfilehash: 32238923aeef14230f68def15e27c676753faf61
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70949543"
---
# <a name="_read"></a>_read

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

*arabelleğin*<br/>
Veriler için depolama konumu.

*buffer_size*<br/>
Okunacak en fazla bayt sayısı.

## <a name="return-value"></a>Dönüş Değeri

**_read** , dosyada *Buffer_size* bayttan daha az veya dosya metin modunda açıldıysa, okunan bayt sayısını döndürür. Bu, *Buffer_size* 'tan daha az olabilir. Metin modunda, her satır başı satır besleme çifti `\r\n` tek satırlık bir besleme karakteriyle `\n`değiştirilmiştir. Dönüş değerinde yalnızca tek satırlık akış karakteri sayılır. Değiştirme dosya işaretçisini etkilemez.

İşlev dosyanın sonunda okumaya çalışırsa, 0 döndürür. *FD* geçerli değilse, dosya okuma için açık değildir veya dosya kilitliyse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, işlev-1 döndürür ve **errno** 'U **EBADF**olarak ayarlar.

*Buffer* **null**ise veya *Buffer_size* > **INT_MAX**ise geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, işlev-1 döndürür ve **errno** , **EINVAL**olarak ayarlanır.

Bu ve diğer dönüş kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Read** işlevi *FD*ile ilişkili dosyadan en fazla *Buffer_size* baytlık *arabelleği* okur. Okuma işlemi, belirtilen dosyayla ilişkili dosya işaretçisinin geçerli konumunda başlar. Okuma işleminden sonra, dosya işaretçisi sonraki okunmamış karakteri işaret eder.

Dosya metin modunda açılırsa, **_read** , dosya sonu göstergesi olarak kabul EDILEN bir CTRL + Z karakteriyle karşılaştığında okuma sonlanır. Dosya sonu göstergesini temizlemek için [_lseek](lseek-lseeki64.md) kullanın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_read**|\<GÇ. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

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

### <a name="input-crt_readtxt"></a>Giriş: crt_read. txt

```Input
Line one.
Line two.
```

### <a name="output"></a>Çıkış

```Output
Read 19 bytes from file
```

## <a name="see-also"></a>Ayrıca bkz.

[Alt düzey g/ç](../../c-runtime-library/low-level-i-o.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[fread](fread.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_write](write.md)<br/>
