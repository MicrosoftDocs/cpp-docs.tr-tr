---
title: _isatty
ms.date: 11/04/2016
apiname:
- _isatty
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
- _isatty
helpviewer_keywords:
- isatty function
- character device checking
- _isatty function
- checking character devices
ms.assetid: 9f1b2e87-0cd7-4079-b187-f2b7ca15fcbe
ms.openlocfilehash: ef0df5f859779c081df47ef4bfe938ec2601d524
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50545593"
---
# <a name="isatty"></a>_isatty

Dosya tanımlayıcısının karakter cihazla ilişkili olup olmadığını belirler.

## <a name="syntax"></a>Sözdizimi

```C
int _isatty( int fd );
```

### <a name="parameters"></a>Parametreler

*FD*<br/>
Test edilecek cihaza başvuran dosya tanımlayıcısı.

## <a name="return-value"></a>Dönüş Değeri

**_isatty** tanımlayıcı bir karakter cihazıyla ilişkiliyse, sıfır olmayan bir değer döndürür. Aksi takdirde, **_isatty** 0 döndürür.

## <a name="remarks"></a>Açıklamalar

**_İsatty** işlevi belirler olmadığını *fd* (bir terminal, konsol, yazıcı veya seri bağlantı noktası) bir karakter cihazıyla ilişkilendirilir.

Bu işlev doğrular *fd* parametresi. Varsa *fd* bir hatalı dosya işaretçisiyse, içinde açıklanan şekilde geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Devam etmek için ayarlar ve işlev 0 döndürür yürütülmesine izin veriliyorsa **errno** için **EBADF**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_isatty**|\<io.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Örnek

```C
// crt_isatty.c
/* This program checks to see whether
* stdout has been redirected to a file.
*/

#include <stdio.h>
#include <io.h>

int main( void )
{
   if( _isatty( _fileno( stdout ) ) )
      printf( "stdout has not been redirected to a file\n" );
   else
      printf( "stdout has been redirected to a file\n");
}
```

### <a name="sample-output"></a>Örnek Çıktı

```Output
stdout has not been redirected to a file
```

## <a name="see-also"></a>Ayrıca bkz.

[Dosya İşleme](../../c-runtime-library/file-handling.md)<br/>
