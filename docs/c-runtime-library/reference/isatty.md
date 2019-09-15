---
title: _isatty
ms.date: 11/04/2016
api_name:
- _isatty
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
ms.openlocfilehash: 2d2ba2fdfeb1c8bffe47b0953f0629746d2eb599
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70954551"
---
# <a name="_isatty"></a>_isatty

Bir dosya tanımlayıcısının bir karakter aygıtıyla ilişkili olup olmadığını belirler.

## <a name="syntax"></a>Sözdizimi

```C
int _isatty( int fd );
```

### <a name="parameters"></a>Parametreler

*FD*<br/>
Sınanacak cihaza başvuran dosya tanımlayıcısı.

## <a name="return-value"></a>Dönüş Değeri

**_ısatty** , tanımlayıcı bir karakter aygıtıyla ilişkiliyse sıfır dışında bir değer döndürür. Aksi takdirde, **_ısatty** 0 değerini döndürür.

## <a name="remarks"></a>Açıklamalar

**_İsatty** işlevi, *FD* 'nin bir karakter aygıtıyla (Terminal, konsol, yazıcı veya seri bağlantı noktası) ilişkili olup olmadığını belirler.

Bu işlev *FD* parametresini doğrular. *FD* hatalı bir dosya Işaretçisiyse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, işlev 0 döndürür ve **errno** 'U **EBADF**olarak ayarlar.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_isatty**|\<GÇ. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

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
