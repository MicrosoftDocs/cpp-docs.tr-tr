---
title: _getw
ms.date: 11/04/2016
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
helpviewer_keywords:
- _getw function
- integers, getting from streams
- getw function
ms.assetid: ef75facc-b84e-470f-9f5f-8746c90822a0
ms.openlocfilehash: 615d3ac9bdc73ad200368eaeabf7c84951bc91ae
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62157636"
---
# <a name="getw"></a>_getw

Bir akıştan tamsayı alır.

## <a name="syntax"></a>Sözdizimi

```C
int _getw(
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*Stream*<br/>
İşaretçi **dosya** yapısı.

## <a name="return-value"></a>Dönüş Değeri

**_getw** okuma Integer değeri döndürür. Dönüş değeri **EOF** bir hata veya dosya sonunu gösterir. Ancak, çünkü **EOF** değeri de yasal bir tamsayı, kullanın **feof** veya **ferror** bir dosya sonu veya hata durumu doğrulamak için. Varsa *stream* olduğu **NULL**, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse **errno** ayarlanır **EINVAL** ve işlev döndürür **EOF**.

## <a name="remarks"></a>Açıklamalar

**_Getw** işlevi türü sonraki ikili değeri okuyan **int** ilişkili dosyasından *stream* ve (varsa) ilgili dosya işaretleyicisini işaret etmek üzere artırır Sonraki okunmamış karaktere. **_getw** akışındaki öğelerin herhangi özel hizalama varsaymaz. Bağlantı noktası oluşturma sorunları meydana gelebilir **_getw** çünkü boyutunu **int** türü ve bayt sıralama **int** türü sistemler arasında farklılık gösterir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_getw**|\<stdio.h >|

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

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[_putw](putw.md)<br/>
