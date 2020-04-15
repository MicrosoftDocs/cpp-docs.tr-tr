---
title: clearerr
ms.date: 4/2/2020
api_name:
- clearerr
- _o_clearerr
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
- clearerr
helpviewer_keywords:
- error indicator for streams
- resetting stream error indicator
- clearerr function
ms.assetid: a9711cd4-3335-43d4-a018-87bbac5b3bac
ms.openlocfilehash: 174c94136cdc8b603416ff1dd239703489925bae
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81350031"
---
# <a name="clearerr"></a>clearerr

Akış için hata göstergesini sıfırlar. Bu işlevin daha güvenli bir sürümü mevcuttur; [bkz. clearerr_s](clearerr-s.md).

## <a name="syntax"></a>Sözdizimi

```C
void clearerr(
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*Akışı*<br/>
**DOSYA** yapısı için işaretçi.

## <a name="remarks"></a>Açıklamalar

Daha **net daha net** *işlev, akış*için hata göstergesini ve dosya sonu göstergesini sıfırlar. Hata göstergeleri otomatik olarak temizlenmez; belirli bir akış için hata göstergesi ayarlandıktan sonra, o akıştaki işlemler daha **net,** [fseek](fseek-fseeki64.md), **fsetpos**veya [geri sarma](rewind.md) adı verilene kadar bir hata değeri döndürmeye devam edin.

*Akış* **NULL**ise, geçersiz parametre işleyicisi, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, bu işlev **EINVAL** **için errno** ayarlar ve döndürür. **Errno** ve hata kodları hakkında daha fazla bilgi için [bkz.](../../c-runtime-library/errno-constants.md)

Bu işlevin daha güvenli bir sürümü mevcuttur; [bkz. clearerr_s](clearerr-s.md).

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**clearerr**|\<stdio.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

```C
// crt_clearerr.c
// This program creates an error
// on the standard input stream, then clears
// it so that future reads won't fail.

#include <stdio.h>

int main( void )
{
   int c;
   // Create an error by writing to standard input.
   putc( 'c', stdin );
   if( ferror( stdin ) )
   {
      perror( "Write error" );
      clearerr( stdin );
   }

   // See if read causes an error.
   printf( "Will input cause an error? " );
   c = getc( stdin );
   if( ferror( stdin ) )
   {
      perror( "Read error" );
      clearerr( stdin );
   }
   else
      printf( "No read error\n" );
}
```

### <a name="input"></a>Girdi

```Input
n
```

### <a name="output"></a>Çıktı

```Output
Write error: No error
Will input cause an error? n
No read error
```

## <a name="see-also"></a>Ayrıca bkz.

[Hata İşleme](../../c-runtime-library/error-handling-crt.md)<br/>
[Akış I/O](../../c-runtime-library/stream-i-o.md)<br/>
[_eof](eof.md)<br/>
[feof](feof.md)<br/>
[ferror](ferror.md)<br/>
[perror, _wperror](perror-wperror.md)<br/>
