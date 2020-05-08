---
title: clearerr_s
ms.date: 4/2/2020
api_name:
- clearerr_s
- _o_clearerr_s
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
- clearerr_s
helpviewer_keywords:
- error indicator for streams
- resetting stream error indicator
- clearerr_s function
ms.assetid: b74d014d-b7a8-494a-a330-e5ffd5614772
ms.openlocfilehash: 3e300562a52029fe835ebd4fe34e9a7ef247a76a
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82917215"
---
# <a name="clearerr_s"></a>clearerr_s

Bir akışın Hata göstergesini sıfırlar. Bu, [CRT 'Daki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleriyle [clearerr](clearerr.md) 'in bir sürümüdür.

## <a name="syntax"></a>Sözdizimi

```C
errno_t clearerr_s(
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*ka*<br/>
**Dosya** yapısına yönelik işaretçi

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır; *Stream* **null**ise **EINVAL** .

## <a name="remarks"></a>Açıklamalar

**Clearerr_s** işlevi, *akış*için hata göstergesini ve dosya sonu göstergesini sıfırlar. Hata göstergeleri otomatik olarak temizlenmez; Belirtilen bir akış için hata göstergesi ayarlandığında, bu akıştaki işlemler **clearerr_s**, **clearerr**, [fseek](fseek-fseeki64.md), **fsetpos**veya [geri sarma](rewind.md) çağrılana kadar bir hata değeri döndürmeye devam eder.

*Stream* **null**ise, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlev **errno** ' ı **EINVAL** olarak ayarlar ve **EINVAL**döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**clearerr_s**|\<stdio. h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_clearerr_s.c
// This program creates an error
// on the standard input stream, then clears
// it so that future reads won't fail.

#include <stdio.h>

int main( void )
{
   int c;
   errno_t err;

   // Create an error by writing to standard input.
   putc( 'c', stdin );
   if( ferror( stdin ) )
   {
      perror( "Write error" );
      err = clearerr_s( stdin );
      if (err != 0)
      {
         abort();
      }
   }

   // See if read causes an error.
   printf( "Will input cause an error? " );
   c = getc( stdin );
   if( ferror( stdin ) )
   {
      perror( "Read error" );
      err = clearerr_s( stdin );
      if (err != 0)
      {
         abort();
      }
   }
}
```

### <a name="input"></a>Girdi

```Input
n
```

### <a name="output"></a>Çıktı

```Output
Write error: Bad file descriptor
Will input cause an error? n
```

## <a name="see-also"></a>Ayrıca bkz.

[Hata Işleme](../../c-runtime-library/error-handling-crt.md)<br/>
[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[clearerr](clearerr.md)<br/>
[_eof](eof.md)<br/>
[feof](feof.md)<br/>
[ferror](ferror.md)<br/>
[perror, _wperror](perror-wperror.md)<br/>
