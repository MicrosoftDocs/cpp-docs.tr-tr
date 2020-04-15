---
title: _isatty
ms.date: 4/2/2020
api_name:
- _isatty
- _o__isatty
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
- _isatty
helpviewer_keywords:
- isatty function
- character device checking
- _isatty function
- checking character devices
ms.assetid: 9f1b2e87-0cd7-4079-b187-f2b7ca15fcbe
ms.openlocfilehash: c9611c2bd55ebc1602a73e4c71518716ea100420
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81343898"
---
# <a name="_isatty"></a>_isatty

Dosya tanımlayıcının bir karakter aygıtıyla ilişkili olup olmadığını belirler.

## <a name="syntax"></a>Sözdizimi

```C
int _isatty( int fd );
```

### <a name="parameters"></a>Parametreler

*Fd*<br/>
Test edilecek aygıta başvuran dosya tanımlayıcısı.

## <a name="return-value"></a>Dönüş Değeri

**_isatty,** tanımlayıcı bir karakter aygıtıyla ilişkiliyse sıfır olmayan bir değer verir. Aksi takdirde, **_isatty** 0 döndürür.

## <a name="remarks"></a>Açıklamalar

**_isatty** işlevi *fd'nin* bir karakter aygıtıyla (terminal, konsol, yazıcı veya seri bağlantı noktası) ilişkili olup olmadığını belirler.

Bu işlev *fd* parametresini doğrular. *fd* hatalı bir dosya işaretçisi ise, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmedevam etmesine izin verilirse, işlev 0 döndürür ve **EBADF** **için errno** ayarlar.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_isatty**|\<io.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="libraries"></a>Kitaplıklar

C çalışma [zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

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

[Dosya Işleme](../../c-runtime-library/file-handling.md)<br/>
