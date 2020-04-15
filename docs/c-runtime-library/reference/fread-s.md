---
title: fread_s
ms.date: 4/2/2020
api_name:
- fread_s
- _o_fread_s
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
- fread_s
- stdio/fread_s
ms.assetid: ce735de0-f005-435d-a8f2-6f4b80ac775e
ms.openlocfilehash: 97f7ca80d4b458b952393a5b1f72bebe0bdb0d9f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81346120"
---
# <a name="fread_s"></a>fread_s

Bir akıştan gelen verileri okur. [Fread'in](fread.md) bu sürümü, [CRT'deki Güvenlik Özellikleri'nde](../../c-runtime-library/security-features-in-the-crt.md)açıklandığı gibi güvenlik geliştirmelerine sahiptir.

## <a name="syntax"></a>Sözdizimi

```C
size_t fread_s(
   void *buffer,
   size_t bufferSize,
   size_t elementSize,
   size_t count,
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*Arabellek*<br/>
Veriler için depolama konumu.

*Buffersize*<br/>
Baytlar'daki hedef arabelleği boyutu.

*elementBoyut*<br/>
Baytokunacak öğenin boyutu.

*Sayısı*<br/>
Okunacak maksimum öğe sayısı.

*Akışı*<br/>
**DOSYA** yapısı için işaretçi.

## <a name="return-value"></a>Dönüş Değeri

**fread_s,** *sayıma* ulaşılmadan önce okuma hatası veya dosyanın sonunda karşılaşılırsa *sayısı* daha az olabilecek arabelleğe okunan (tam) öğe sayısını döndürür. Bir hatayı dosya sonu durumundan ayırmak için **feof** veya **ferror** işlevini kullanın. *Boyut* veya *sayım* 0 ise, **fread_s** 0 döndürür ve arabellek içeriği değişmez. *Akış* veya *arabellek* null işaretçisi ise, **fread_s** [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin verilirse, bu işlev **errno'u** **EINVAL'e** ayarlar ve 0 döndürür.

Hata kodları hakkında daha fazla bilgi için [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)bakın.

## <a name="remarks"></a>Açıklamalar

**fread_s** işlevi, giriş *akışındaki* *elementSize* bayt öğelerini *saymak* için yukarı okur ve bunları *arabellekte*depolar.  *Akışla* ilişkili dosya işaretçisi (varsa) gerçekten okunan bayt sayısıyla artar. Verilen akış metin modunda açılırsa, satır satır besleme çiftleri tek satır besleme karakterleri ile değiştirilir. Değiştirmenin dosya işaretçisi veya iade değeri üzerinde hiçbir etkisi yoktur. Bir hata oluşursa dosya işaretçisi konumu belirsizdir. Kısmen okunan öğenin değeri belirlenemez.

Bu işlev diğer iş parçacıklarını kilitler. Kilitlenmeyen bir sürüm gerekiyorsa, **_fread_nolock**kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fread_s**|\<stdio.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

```cpp
// crt_fread_s.c
// Command line: cl /EHsc /nologo /W4 crt_fread_s.c
//
// This program opens a file that's named FREAD.OUT and
// writes characters to the file. It then tries to open
// FREAD.OUT and read in characters by using fread_s. If the attempt succeeds,
// the program displays the number of actual items read.

#include <stdio.h>

#define BUFFERSIZE 30
#define DATASIZE 22
#define ELEMENTCOUNT 2
#define ELEMENTSIZE (DATASIZE/ELEMENTCOUNT)
#define FILENAME "FREAD.OUT"

int main( void )
{
   FILE *stream;
   char list[30];
   int  i, numread, numwritten;

   for ( i = 0; i < DATASIZE; i++ )
      list[i] = (char)('z' - i);
   list[DATASIZE] = '\0'; // terminal null so we can print it

   // Open file in text mode:
   if( fopen_s( &stream, FILENAME, "w+t" ) == 0 )
   {
      // Write DATASIZE characters to stream
      printf( "Contents of buffer before write/read:\n\t%s\n\n", list );
      numwritten = fwrite( list, sizeof( char ), DATASIZE, stream );
      printf( "Wrote %d items\n\n", numwritten );
      fclose( stream );
   } else {
      printf( "Problem opening the file\n" );
      return -1;
   }

   if( fopen_s( &stream, FILENAME, "r+t" ) == 0 )   {
      // Attempt to read in characters in 2 blocks of 11
      numread = fread_s( list, BUFFERSIZE, ELEMENTSIZE, ELEMENTCOUNT, stream );
      printf( "Number of %d-byte elements read = %d\n\n", ELEMENTSIZE, numread );
      printf( "Contents of buffer after write/read:\n\t%s\n", list );
      fclose( stream );
   } else {
      printf( "File could not be opened\n" );
      return -1;
   }
}
```

```Output
Contents of buffer before write/read:
        zyxwvutsrqponmlkjihgfe

Wrote 22 items

Number of 11-byte elements read = 2

Contents of buffer after write/read:
        zyxwvutsrqponmlkjihgfe
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fwrite](fwrite.md)<br/>
[_read](read.md)<br/>
