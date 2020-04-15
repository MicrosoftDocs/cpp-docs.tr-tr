---
title: _read
ms.date: 4/2/2020
api_name:
- _read
- _o__read
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
- _read
helpviewer_keywords:
- data [CRT]
- _read function
- read function
- data [C++], reading
- reading data [C++]
- files [C++], reading
ms.assetid: 2ce9c433-57ad-47fe-9ac1-4a7d4c883d30
ms.openlocfilehash: db3726b85bb4ba7c8e9a691bef3fb063ec5709c9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338127"
---
# <a name="_read"></a>_read

Dosyadaki verileri okur.

## <a name="syntax"></a>Sözdizimi

```C
int _read(
   int const fd,
   void * const buffer,
   unsigned const buffer_size
);
```

### <a name="parameters"></a>Parametreler

*Fd*<br/>
Açık dosyaya atıfta bulunan dosya tanımlayıcısı.

*Arabellek*<br/>
Veriler için depolama konumu.

*buffer_size*<br/>
Okunacak maksimum bayt sayısı.

## <a name="return-value"></a>Dönüş Değeri

**_read,** dosyada *buffer_size* bayttan az kalmışsa veya dosya metin modunda açılmışsa *buffer_size'den* az olabilecek okunan bayt sayısını döndürür. Metin modunda, her satır satır `\r\n` besleme çifti tek bir satır `\n`besleme karakteri ile değiştirilir. İade değerinde yalnızca tek satır besleme karakteri sayılır. Değiştirme dosya işaretçisini etkilemez.

İşlev dosyanın sonunda okumaya çalışırsa, 0 döndürür. *fD* geçerli değilse, dosya okumak için açık değilse veya dosya kilitliyse, geçersiz parametre işleyicisi [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, işlev -1 döndürür ve **EBADF** **için errno** ayarlar.

*Arabellek* **NULL**ise veya *buffer_size* > **INT_MAX,** geçersiz parametre işleyicisi çağrılır. Yürütmedevam etmesine izin verilirse, işlev -1 döndürür ve **errno** **EINVAL**olarak ayarlanır.

Bu ve diğer iade kodları hakkında daha fazla bilgi için [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)bakın.

## <a name="remarks"></a>Açıklamalar

**_read** işlevi *fd*ile ilişkili dosyadan *arabellek* içine *buffer_size* bayt maksimum okur. Okuma işlemi, verilen dosyayla ilişkili dosya işaretçisinin geçerli konumunda başlar. Okuma işleminden sonra, dosya işaretçisi bir sonraki okunmamış karakteri işaret eder.

Dosya metin modunda açılmışsa, **_read** dosya sonu göstergesi olarak kabul edilen bir CTRL+Z karakteriyle karşılaştığında okuma sona erer. Dosya sonu göstergesini temizlemek için [_lseek](lseek-lseeki64.md) kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_read**|\<io.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="libraries"></a>Kitaplıklar

C çalışma [zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

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

### <a name="input-crt_readtxt"></a>Giriş: crt_read.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>Çıktı

```Output
Read 19 bytes from file
```

## <a name="see-also"></a>Ayrıca bkz.

[Düşük Seviyeli G/Ç](../../c-runtime-library/low-level-i-o.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[fread](fread.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_write](write.md)<br/>
