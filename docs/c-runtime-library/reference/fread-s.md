---
title: fread_s
ms.date: 11/04/2016
apiname:
- fread_s
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
- fread_s
- stdio/fread_s
ms.assetid: ce735de0-f005-435d-a8f2-6f4b80ac775e
ms.openlocfilehash: 898e813c19fd53cfdacd536c2e9819743a62a8da
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62287817"
---
# <a name="freads"></a>fread_s

Verileri bir akıştan okur. Bu sürümü [fread](fread.md) açıklandığı gibi güvenlik geliştirmeleri vardır [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

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
Veri için depolama konumu.

*BufferSize*<br/>
Hedef arabelleğin bayt cinsinden boyutu.

*elementSize*<br/>
Okunan bayt öğe boyutu.

*Sayısı*<br/>
Okunacak öğe maksimum sayısı.

*Stream*<br/>
İşaretçi **dosya** yapısı.

## <a name="return-value"></a>Dönüş Değeri

**fread_s** olabilen arabelleğine okunan (tam) sayısı öğeleri döndürür küçüktür *sayısı* okuma hatası ya da dosyanın sonunda önce karşılaşılırsa *sayısı* ulaşıldı. Kullanım **feof** veya **ferror** hata bir dosya sonu koşulunu ayırt etmek için işlevi. Varsa *boyutu* veya *sayısı* 0 ' dır **fread_s** 0 ve arabellek içeriği değişmeden döndürür. Varsa *stream* veya *arabellek* null bir işaretçiyse, **fread_s** açıklandığı gibi geçersiz parametre işleyicisini çağırır [Parameter Validation](../../c-runtime-library/parameter-validation.md) . Yürütme devam etmesine izin verilirse, bu işlev ayarlar **errno** için **EINVAL** ve 0 döndürür.

Hata kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**Fread_s** işlevi okur kadar *sayısı* öğelerin *elementSize* girdisinden bayt *stream* ve içinde depolar*arabellek*.  İle ilişkili dosya işaretçisini *stream* (varsa) tarafından gerçekten okunan bayt sayısı artar. Belirtilen akış metin modunda açılırsa, satır başı satır besleme çiftleri tek bir satır başı besleme karakterleri ile değiştirilir. Değiştirilen dosya işaretçisini ya da dönüş değeri üzerinde etkisi yoktur. Dosya işaretçisi olarak bir hata oluşursa belirsiz konumdur. Kısmen okuma öğesinin değeri belirlenemiyor.

Bu işlev, diğer iş parçacıklarını kilitler. Kilitleme yapılmayan bir sürüm gerektirir, kullanın **_fread_nolock**.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fread_s**|\<stdio.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fwrite](fwrite.md)<br/>
[_read](read.md)<br/>
