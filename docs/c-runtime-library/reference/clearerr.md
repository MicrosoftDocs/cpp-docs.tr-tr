---
description: 'Daha fazla bilgi edinin: clearerr'
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 3085039b142f4aa5eec84259626deef961e37fa0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97260793"
---
# <a name="clearerr"></a>clearerr

Bir akışın Hata göstergesini sıfırlar. Bu işlevin daha güvenli bir sürümü kullanılabilir; bkz. [clearerr_s](clearerr-s.md).

## <a name="syntax"></a>Sözdizimi

```C
void clearerr(
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*ka*<br/>
**Dosya** yapısına yönelik işaretçi.

## <a name="remarks"></a>Açıklamalar

**Clearerr** işlevi, *akış* için hata göstergesini ve dosya sonu göstergesini sıfırlar. Hata göstergeleri otomatik olarak temizlenmez; Belirtilen bir akış için hata göstergesi ayarlandığında, bu akıştaki işlemler **clearerr**, [fseek](fseek-fseeki64.md), **fsetpos** veya [geri sarma](rewind.md) çağrılana kadar bir hata değeri döndürmeye devam eder.

*Stream* **null** ise, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlev **errno** ' ı **EINVAL** ve döndürür. **Errno** ve hata kodları hakkında daha fazla bilgi için bkz. [errno sabitleri](../../c-runtime-library/errno-constants.md).

Bu işlevin daha güvenli bir sürümü kullanılabilir; bkz. [clearerr_s](clearerr-s.md).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**clearerr**|\<stdio.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

[Hata Işleme](../../c-runtime-library/error-handling-crt.md)<br/>
[Akış G/Ç](../../c-runtime-library/stream-i-o.md)<br/>
[_eof](eof.md)<br/>
[feof](feof.md)<br/>
[ferror](ferror.md)<br/>
[perror, _wperror](perror-wperror.md)<br/>
