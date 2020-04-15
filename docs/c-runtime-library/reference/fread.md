---
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 26ffd56072f1a5fddc3131a42cd47c145e437b60
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81346061"
---
# <a name="fread"></a>fread

Bir akıştan gelen verileri okur.

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
Veriler için depolama konumu.

*Boyutu*<br/>
Baytlarda madde boyutu.

*Sayısı*<br/>
Okunacak maksimum öğe sayısı.

*Akışı*<br/>
**DOSYA** yapısı için işaretçi.

## <a name="return-value"></a>Dönüş Değeri

**fread,** bir hata oluşursa veya *sayıma*ulaşmadan önce dosyanın sonuyla *karşılaşılırsa,* gerçekte okunan tam öğe sayısını döndürür. Okuma hatasını dosya sonu durumundan ayırmak için **feof** veya **ferror** işlevini kullanın. *Boyut* veya *sayım* 0 ise, **fread** 0 döndürür ve arabellek içeriği değişmez. *Akış* veya *arabellek* null işaretçisi ise, **Fread** [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin verilirse, bu işlev **errno'u** **EINVAL'e** ayarlar ve 0 döndürür.

Bu hata kodları hakkında daha fazla bilgi için [ \_doserrno, errno, \_sys\_errlist ve \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bakın.

## <a name="remarks"></a>Açıklamalar

**Fread** işlevi, giriş *akışındaki* *boyut* baytöğelerini *saymak* için yukarı okur ve bunları *arabellekte*depolar. *Akışla* ilişkili dosya işaretçisi (varsa) gerçekten okunan bayt sayısıyla artar. Verilen akış [metin modunda](../../c-runtime-library/text-and-binary-mode-file-i-o.md)açılırsa, Windows tarzı yeni satırlar Unix tarzı yeni satırlara dönüştürülür. Diğer bir arada, satır satır besleme (CRLF) çiftleri tek satır besleme (LF) karakterleri ile değiştirilir. Değiştirmenin dosya işaretçisi veya iade değeri üzerinde hiçbir etkisi yoktur. Bir hata oluşursa dosya işaretçisi konumu belirsizdir. Kısmen okunan öğenin değeri belirlenemez.

Metin modu akışında kullanıldığında, istenen veri miktarı (yani *boyut* \* *sayısı)* iç **DOSYA** \* arabelleği boyutundan büyük veya eşitse (varsayılan olarak bu 4096 bayttır, [setvbuf](../../c-runtime-library/reference/setvbuf.md)kullanılarak yapılandırılabilir), akış verileri doğrudan kullanıcı tarafından sağlanan arabelleğe kopyalanır ve bu arabellekte yeni satır dönüştürme yapılır. Dönüştürülen veriler arabelleğe kopyalanan akış verilerinden daha kısa olabileceğinden, *arabellek*\[*return_value* \* *boyutu*] **(return_value'nin fread'ten**gelen geri dönüş değeri olduğu) dosyadan dönüştürülmemiş veriler içerebilir. *return_value* Bu nedenle, arabellek amacı C stili dize olarak hareket etmek ise, *arabellek*\[*return_value* \* *boyutu*] karakter verilerini geçersiz sonlandırmanızı öneririz. Metin modu ve ikili modun etkileri hakkında ayrıntılı bilgi için [açık](fopen-wfopen.md) bakınız.

Bu işlev diğer iş parçacıklarını kilitler. Kilitlenmeyen bir sürüme ihtiyacınız varsa, **_fread_nolock**kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fread**|\<stdio.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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

[Akış I/O](../../c-runtime-library/stream-i-o.md)<br/>
[Metin ve İkili Dosya I/O](../../c-runtime-library/text-and-binary-mode-file-i-o.md)<br/>
[Fopen](fopen-wfopen.md)<br/>
[fwrite](fwrite.md)<br/>
[_read](read.md)<br/>
