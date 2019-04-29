---
title: feof
ms.date: 11/04/2016
apiname:
- feof
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
- feof
helpviewer_keywords:
- end of file, testing for
- feof function
ms.assetid: 09081eee-7c4b-4189-861f-2fad95d3ec6d
ms.openlocfilehash: 9c023290df601bfc48f9708af86d32d91cd52dc4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62334404"
---
# <a name="feof"></a>feof

Son dosya akışı ile ilgili sınar.

## <a name="syntax"></a>Sözdizimi

```C
int feof(
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*Stream*<br/>
İşaretçi **dosya** yapısı.

## <a name="return-value"></a>Dönüş Değeri

**Feof** işlevi okuma işlemi dosyanın sonundan okumayı denedi, sıfır olmayan bir değer döndürür; Aksi takdirde 0 değerini döndürür. Akış işaretçisini ise **NULL**, işlev içinde açıklanan şekilde geçersiz parametre işleyicisi çağırır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse **errno** ayarlanır **EINVAL** ve **feof** 0 döndürür.

Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu ve diğer hata kodları hakkında daha fazla bilgi için.

## <a name="remarks"></a>Açıklamalar

**Feof** belirler (hem bir işlev ve makro olarak uygulanmış) yordamı olmadığını sonuna *stream* geçirildi. Dosya sonu geçirildiğinde, akış kapatılana kadar veya kadar operations dönen bir dosya sonu göstergesi okuma [rewind](rewind.md), **fsetpos**, [fseek](fseek-fseeki64.md), veya  **clearerr** göre adlandırılır.

Örneğin, 10 bayta bir dosya içeriyorsa ve 10 bayt Dosyadan okuma **feof** dosya işaretçisini dosyanın sonunda olsa bile, son okuma girişiminde bulundunuz değil çünkü 0 döndürür. Okunacak çalıştıktan sonra bir 11 bayt olur yalnızca **feof** sıfır olmayan bir değer döndürür.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**feof**|\<stdio.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_feof.c
// This program uses feof to indicate when
// it reaches the end of the file CRT_FEOF.TXT. It also
// checks for errors with ferror.
//

#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   int  count, total = 0;
   char buffer[100];
   FILE *stream;

   fopen_s( &stream, "crt_feof.txt", "r" );
   if( stream == NULL )
      exit( 1 );

   // Cycle until end of file reached:
   while( !feof( stream ) )
   {
      // Attempt to read in 100 bytes:
      count = fread( buffer, sizeof( char ), 100, stream );
      if( ferror( stream ) )      {
         perror( "Read error" );
         break;
      }

      // Total up actual bytes read
      total += count;
   }
   printf( "Number of bytes read = %d\n", total );
   fclose( stream );
}
```

## <a name="input-crtfeoftxt"></a>Giriş: crt_feof.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>Çıkış

```Output
Number of bytes read = 19
```

## <a name="see-also"></a>Ayrıca bkz.

[Hata İşleme](../../c-runtime-library/error-handling-crt.md)<br/>
[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[clearerr](clearerr.md)<br/>
[_eof](eof.md)<br/>
[ferror](ferror.md)<br/>
[perror, _wperror](perror-wperror.md)<br/>
