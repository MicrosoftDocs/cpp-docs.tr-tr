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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: eddb68ae6108c8a66966472cebca60a9969b78d1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344158"
---
# <a name="_getw"></a>_getw

Bir akıştan bir tamsayı alır.

## <a name="syntax"></a>Sözdizimi

```C
int _getw(
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*Akışı*<br/>
**DOSYA** yapısına işaretçi.

## <a name="return-value"></a>Dönüş Değeri

**_getw,** okunan tamsayı değerini döndürür. **EOF'nin** iade değeri bir hatayı veya dosya sonunu gösterir. Ancak, **EOF** değeri de yasal bir tamsayı değeri olduğundan, dosya sonu veya hata durumunu doğrulamak için **feof** veya **ferror** kullanın. *Akış* **NULL**ise, geçersiz parametre işleyicisi, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, **errno** **EINVAL** olarak ayarlanır ve işlev **EOF**döndürür.

## <a name="remarks"></a>Açıklamalar

**_getw** *işlevi, akışla* ilişkili dosyadan tür **int'in** bir sonraki ikili değerini okur ve bir sonraki okunmamış karaktere işaret etmek için ilişkili dosya işaretçisini (varsa) artışlar. **_getw** akıştaki öğelerin özel bir hizalamasını kabul etmez. **Int** türündeki baytların boyutu ve bayt ların sıralanması sistemler arasında **int** farklılık gösterir. **_getw**

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_getw**|\<stdio.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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

### <a name="input-crt_getwtxt"></a>Giriş: crt_getw.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>Çıktı

```Output
First data word in file: 0x656e694c
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış I/O](../../c-runtime-library/stream-i-o.md)<br/>
[_putw](putw.md)<br/>
