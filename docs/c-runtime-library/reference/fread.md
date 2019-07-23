---
title: fread
ms.date: 11/28/2018
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
ms.openlocfilehash: da3828142a06ed89a6447ccaef4a0d8ff0063cca
ms.sourcegitcommit: 878a164fe6d550ca81ab87d8425c8d3cd52fe384
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/22/2019
ms.locfileid: "68376173"
---
# <a name="fread"></a>fread

Akıştan verileri okur.

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

*arabelleğin*<br/>
Veriler için depolama konumu.

*boyutla*<br/>
Bayt cinsinden öğe boyutu.

*biriktirme*<br/>
Okunacak en fazla öğe sayısı.

*ka*<br/>
**Dosya** yapısına yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

**fread** , gerçekten okunan tam öğe sayısını döndürür. Bu, bir hata oluşursa veya dosyanın sonuna *sayıma*ulaşılmadan önce *Bu sayıdan daha* az olabilir. Bir okuma hatasını bir dosya sonu koşulunun ayırt etmek için **feof** veya **ferror** işlevini kullanın. *Boyut* veya *sayı* 0 ise, **fread** 0 döndürür ve arabellek içeriği değiştirilmez. *Stream* veya *buffer* null bir işaretçisiyse, **fread** [parametresi doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, bu işlev **errno** ' ı **EINVAL** olarak ayarlar ve 0 döndürür.

Bu hata kodları hakkında daha fazla bilgi için bkz [ \_.\_doserrno \_,\_errno, \_sys errlist ve sys NERR](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) .

## <a name="remarks"></a>Açıklamalar

**Fread** işlevi, giriş *akışındaki* *Boyut* baytlarının öğelerini *saymak* ve *arabelleğe*kaydeder. *Stream* ile ilişkili dosya işaretçisi (varsa), gerçekten okunan bayt sayısıyla artırılır. Verilen akış [metin modunda](../../c-runtime-library/text-and-binary-mode-file-i-o.md)açılırsa, Windows stili newlines, UNIX stili newlines olarak dönüştürülür. Diğer bir deyişle, satır başı satır besleme (CRLF) çiftleri tek satırlık akış (LF) karakterleriyle değiştirilmiştir. Değiştirme işleminin dosya işaretçisi veya dönüş değeri üzerinde hiçbir etkisi yoktur. Bir hata oluşursa dosya işaretçisi konumu belirsiz olur. Kısmen okunan öğenin değeri belirlenemiyor.

Metin modundaki bir akışta kullanıldığında, istenen veri miktarı (yani *Boyut* \* *sayısı*) dahili **Dosya** \* arabelleği boyutundan büyük veya buna eşitse (varsayılan olarak bu 4096 bayttır, kullanılarak [yapılandırılabilir setvbuffer](../../c-runtime-library/reference/setvbuf.md)), akış verileri doğrudan Kullanıcı tarafından sağlanmış arabelleğe kopyalanır ve bu arabellekte yeni satır dönüştürme yapılır. Dönüştürülen veriler, arabelleğe kopyalanmış akış verilerinden daha kısa olabileceğinden, veri geçmiş *arabelleği*\[*RETURN_VALUE* \* *size*] (burada *RETURN_VALUE* , **fread**'ten döndürülen değer) olabilir dosyadan Dönüştürülmeyen verileri içerir. Bu nedenle, arabelleğin amacı C stili bir dize olarak davranıyorsa, *arabellek*\[*RETURN_VALUE* \* *boyutu*] üzerinde null-Terminate karakter verisi kullanmanızı öneririz. Metin modunun ve ikili modun etkileri hakkında ayrıntılı bilgi için bkz. [fopen](fopen-wfopen.md) .

Bu işlev diğer iş parçacıklarını kilitler. Kilitleme dışı bir sürüme ihtiyacınız varsa **_fread_nolock**kullanın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fread**|\<stdio. h >|

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

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[Metin ve Ikili dosya g/ç](../../c-runtime-library/text-and-binary-mode-file-i-o.md)<br/>
[fopen](fopen-wfopen.md)<br/>
[fwrite](fwrite.md)<br/>
[_read](read.md)<br/>
