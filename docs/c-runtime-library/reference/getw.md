---
title: _getw | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _getw
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
- _getw
dev_langs:
- C++
helpviewer_keywords:
- _getw function
- integers, getting from streams
- getw function
ms.assetid: ef75facc-b84e-470f-9f5f-8746c90822a0
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2079672548a7f25106e7540580b60ac9fead8a36
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="getw"></a>_getw

Tamsayı bir akıştan alır.

## <a name="syntax"></a>Sözdizimi

```C
int _getw(
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*Akış*<br/>
İşaretçi **dosya** yapısı.

## <a name="return-value"></a>Dönüş Değeri

**_getw** okuma Integer değeri döndürür. Dönüş değeri **EOF** bir hata veya dosya sonu gösterir. Ancak, çünkü **EOF** değeri de yasal tamsayı değeri, kullanın **feof** veya **ferror** bir dosya sonu veya hata durumu doğrulanamadı. Varsa *akış* olan **NULL**, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa **errno** ayarlanır **EINVAL** ve işlevi döndürür **EOF**.

## <a name="remarks"></a>Açıklamalar

**_Getw** işlevi türü sonraki ikili değeri okuyan **int** ilişkili dosyasından *akış* ve (varsa), ilişkili dosya işaretçisi işaret edecek şekilde artırır Sonraki okunmamış karakter. **_getw** akış öğelerini özel herhangi hizalamasını varsaymaz. Bağlantı noktası oluşturma sorunları meydana gelebilir **_getw** çünkü boyutunu **int** türü ve baytları sipariş **int** türü sistemlerden farklılık gösterir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_getw**|\<stdio.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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

### <a name="input-crtgetwtxt"></a>Giriş: crt_getw.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>Çıkış

```Output
First data word in file: 0x656e694c
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[_putw](putw.md)<br/>
