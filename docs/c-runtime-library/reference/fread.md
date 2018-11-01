---
title: fread
ms.date: 11/04/2016
apiname:
- fread
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
- fread
helpviewer_keywords:
- reading data [C++], from input streams
- fread function
- data [C++], reading from input stream
- streams [C++], reading data from
ms.assetid: 9a3c1538-93dd-455e-ae48-77c1e23c53f0
ms.openlocfilehash: d3516dc67047064b9293b1bb289888596736ed47
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50468841"
---
# <a name="fread"></a>fread

Verileri bir akıştan okur.

## <a name="syntax"></a>Sözdizimi

```C
size_t fread(
   void *buffer,
   size_t size,
   size_t count,
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*Arabellek*<br/>
Veri için depolama konumu.

*Boyutu*<br/>
Bayt olarak öğe boyutu.

*Sayısı*<br/>
Okunacak öğe maksimum sayısı.

*Stream*<br/>
İşaretçi **dosya** yapısı.

## <a name="return-value"></a>Dönüş Değeri

**fread** olabilecek tam öğe sayısını aslında okumak, döndürür küçüktür *sayısı* bir hata oluşursa veya dosya sonuna ulaşmadan önce karşılaşılırsa *sayısı*. Kullanım **feof** veya **ferror** okuma hatası bir dosya sonu koşulunu ayırt etmek için işlevi. Varsa *boyutu* veya *sayısı* 0 ' dır **fread** 0 ve arabellek içeriği değişmeden döndürür. Varsa *stream* veya *arabellek* null bir işaretçiyse, **fread** açıklandığı gibi geçersiz parametre işleyicisini çağırır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütme devam etmesine izin verilirse, bu işlev ayarlar **errno** için **EINVAL** ve 0 döndürür.

Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu ve diğer hata kodları hakkında daha fazla bilgi için.

## <a name="remarks"></a>Açıklamalar

**Fread** işlevi okur kadar *sayısı* öğelerin *boyutu* girdisinden bayt *stream* ve depolar *arabelleği* . İle ilişkili dosya işaretçisini *stream* (varsa) tarafından gerçekten okunan bayt sayısı artar. Belirtilen akış metin modunda açılırsa, satır başı satır besleme çiftleri tek bir satır başı besleme karakterleri ile değiştirilir. Değiştirilen dosya işaretçisini ya da dönüş değeri üzerinde etkisi yoktur. Dosya işaretçisi olarak bir hata oluşursa belirsiz konumdur. Kısmen okuma öğesinin değeri belirlenemiyor.

Bu işlev, diğer iş parçacıklarını kilitler. Kilitleme yapılmayan bir sürüm ihtiyacınız varsa, **_fread_nolock**.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fread**|\<stdio.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_fread.c
// This program opens a file named FREAD.OUT and
// writes 25 characters to the file. It then tries to open
// FREAD.OUT and read in 25 characters. If the attempt succeeds,
// the program displays the number of actual items read.

#include <stdio.h>

int main( void )
{
   FILE *stream;
   char list[30];
   int  i, numread, numwritten;

   // Open file in text mode:
   if( fopen_s( &stream, "fread.out", "w+t" ) == 0 )
   {
      for ( i = 0; i < 25; i++ )
         list[i] = (char)('z' - i);
      // Write 25 characters to stream
      numwritten = fwrite( list, sizeof( char ), 25, stream );
      printf( "Wrote %d items\n", numwritten );
      fclose( stream );

   }
   else
      printf( "Problem opening the file\n" );

   if( fopen_s( &stream, "fread.out", "r+t" ) == 0 )
   {
      // Attempt to read in 25 characters
      numread = fread( list, sizeof( char ), 25, stream );
      printf( "Number of items read = %d\n", numread );
      printf( "Contents of buffer = %.25s\n", list );
      fclose( stream );
   }
   else
      printf( "File could not be opened\n" );
}
```

```Output
Wrote 25 items
Number of items read = 25
Contents of buffer = zyxwvutsrqponmlkjihgfedcb
```

## <a name="see-also"></a>Ayrıca bkz.

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fwrite](fwrite.md)<br/>
[_read](read.md)<br/>
