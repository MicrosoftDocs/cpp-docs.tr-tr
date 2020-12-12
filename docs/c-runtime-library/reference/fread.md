---
description: 'Daha fazla bilgi edinin: fread'
title: fread
ms.date: 4/2/2020
api_name:
- fread
- _o_fread
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- fread
helpviewer_keywords:
- reading data [C++], from input streams
- fread function
- data [C++], reading from input stream
- streams [C++], reading data from
ms.assetid: 9a3c1538-93dd-455e-ae48-77c1e23c53f0
ms.openlocfilehash: 131dacd296d4e710ea1b91d9a8578ef06b76a341
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314054"
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

**fread** , gerçekten okunan tam öğe sayısını döndürür. Bu, bir hata oluşursa veya dosyanın sonuna *sayıma* ulaşılmadan önce *Bu sayıdan daha* az olabilir. Bir okuma hatasını bir dosya sonu koşulunun ayırt etmek için **feof** veya **ferror** işlevini kullanın. *Boyut* veya *sayı* 0 ise, **fread** 0 döndürür ve arabellek içeriği değiştirilmez. *Stream* veya *buffer* null bir işaretçisiyse, **fread** [parametresi doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, bu işlev **errno** ' ı **EINVAL** olarak ayarlar ve 0 döndürür.

Bu hata kodları hakkında daha fazla bilgi için bkz. [ \_ doserrno, errno, \_ sys \_ errlist ve \_ sys \_ NERR](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) .

## <a name="remarks"></a>Açıklamalar

**Fread** işlevi, giriş *akışındaki* *Boyut* baytlarının öğelerini *saymak* ve *arabelleğe* kaydeder. *Stream* ile ilişkili dosya işaretçisi (varsa), gerçekten okunan bayt sayısıyla artırılır. Verilen akış [metin modunda](../../c-runtime-library/text-and-binary-mode-file-i-o.md)açılırsa, Windows stili newlines, UNIX stili newlines olarak dönüştürülür. Diğer bir deyişle, satır başı satır besleme (CRLF) çiftleri tek satırlık akış (LF) karakterleriyle değiştirilmiştir. Değiştirme işleminin dosya işaretçisi veya dönüş değeri üzerinde hiçbir etkisi yoktur. Bir hata oluşursa dosya işaretçisi konumu belirsiz olur. Kısmen okunan öğenin değeri belirlenemiyor.

Metin modundaki bir akışta kullanıldığında, istenen veri miktarı (yani *Boyut* \* *sayısı*) iç **Dosya** arabelleği boyutundan büyük veya buna eşitse \* (varsayılan olarak, bu 4096 bayttır, [setvbuffer](../../c-runtime-library/reference/setvbuf.md)kullanılarak yapılandırılabilir), akış verileri doğrudan Kullanıcı tarafından sağlanmış arabelleğe kopyalanır ve bu arabellekte yeni satır dönüştürme yapılır. Dönüştürülen veriler, arabelleğe kopyalanmış akış verilerinden daha kısa olabileceğinden, veri geçmiş *arabelleği* \[ *RETURN_VALUE* \* *boyutu*] ( *RETURN_VALUE* , **fread**'ten döndürülen değer) dosyadan Dönüştürülmeyen verileri içerebilir. Bu nedenle,  \[  \* arabelleğin amacı C stili bir dize olarak davranıyorsa, arabellek RETURN_VALUE *boyutu*] noktasında null-sonlandırma karakter verisi kullanmanızı öneririz. Metin modunun ve ikili modun etkileri hakkında ayrıntılı bilgi için bkz. [fopen](fopen-wfopen.md) .

Bu işlev diğer iş parçacıklarını kilitler. Kilitleme dışı bir sürüme ihtiyacınız varsa **_fread_nolock** kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fread**|\<stdio.h>|

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

[Akış G/Ç](../../c-runtime-library/stream-i-o.md)<br/>
[Metin ve Ikili dosya g/ç](../../c-runtime-library/text-and-binary-mode-file-i-o.md)<br/>
[fopen](fopen-wfopen.md)<br/>
[fwrite](fwrite.md)<br/>
[_read](read.md)<br/>
