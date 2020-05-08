---
title: _getw
ms.date: 4/2/2020
api_name:
- _getw
- _o__getw
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
- _getw
helpviewer_keywords:
- _getw function
- integers, getting from streams
- getw function
ms.assetid: ef75facc-b84e-470f-9f5f-8746c90822a0
ms.openlocfilehash: fc1dfcc54259dfe40d2fc37be1e1c0ab63ab7c4a
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82916321"
---
# <a name="_getw"></a>_getw

Akıştan bir tamsayı alır.

## <a name="syntax"></a>Sözdizimi

```C
int _getw(
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*ka*<br/>
**Dosya** yapısına yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

**_getw** , okunan tamsayı değerini döndürür. **EOF** dönüş değeri bir hata ya da dosya sonunu gösterir. Ancak, **EOF** değeri de yasal bir tamsayı değeri olduğundan, dosya sonu veya hata koşulunu doğrulamak için **feof** veya **ferror** kullanın. *Stream* **null**ise, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, **errno** **EINVAL** olarak ayarlanır ve işlev **EOF**döndürür.

## <a name="remarks"></a>Açıklamalar

**_Getw** işlevi, *Stream* ile ilişkili dosyadan **int** türünde bir sonraki ikili değeri okur ve bir sonraki okunmamış karakteri işaret eden ilişkili dosya işaretçisini (varsa) artırır. **_getw** akıştaki öğelerin herhangi bir özel hizalamasını varsaymaz. **İnt** türünün boyutu ve **int** türü içindeki bayt sıralaması sistemler arasında farklı olduğundan, taşıma ile ilgili sorunlar **_getw** oluşabilir.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_getw**|\<stdio. h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_getw.c
// This program uses _getw to read a word
// from a stream, then performs an error check.

#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   FILE *stream;
   int i;

   if( fopen_s( &stream, "crt_getw.txt", "rb" ) )
      printf( "Couldn't open file\n" );
   else
   {
      // Read a word from the stream:
      i = _getw( stream );

      // If there is an error...
      if( ferror( stream ) )
      {
         printf( "_getw failed\n" );
         clearerr_s( stream );
      }
      else
         printf( "First data word in file: 0x%.4x\n", i );
      fclose( stream );
   }
}
```

### <a name="input-crt_getwtxt"></a>Giriş: crt_getw. txt

```Input
Line one.
Line two.
```

### <a name="output"></a>Çıktı

```Output
First data word in file: 0x656e694c
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[_putw](putw.md)<br/>
