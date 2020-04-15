---
title: _tell, _telli64
ms.date: 4/2/2020
api_name:
- _telli64
- _tell
- _o__tell
- _o__telli64
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
- telli64
- _telli64
- _tell
helpviewer_keywords:
- tell function
- file pointers [C++], getting
- _tell function
- file pointers [C++]
- telli64 function
- _telli64 function
ms.assetid: 1500e8f9-8fec-4253-9eec-ec66125dfc9b
ms.openlocfilehash: 111d5745703d15fccf0b2a941248203cc80d07a2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81362551"
---
# <a name="_tell-_telli64"></a>_tell, _telli64

Dosya işaretçisinin konumunu alın.

## <a name="syntax"></a>Sözdizimi

```C
long _tell(
   int handle
);
__int64 _telli64(
   int handle
);
```

### <a name="parameters"></a>Parametreler

*Işlemek*<br/>
Dosya tanımlayıcısı açık dosyaya atıfta bulunarak.

## <a name="return-value"></a>Dönüş Değeri

Dosya işaretçisinin geçerli konumu. Arama yapamayan aygıtlarda iade değeri tanımsızdır.

-1L'nin geri dönüş değeri bir hatayı gösterir. *Tanıtıcı* geçersiz bir dosya tanımlayıcısıise, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmedevam etmesine izin verilirse, bu işlevler **EBADF** ve return -1L **errno** ayarlayın.

Bu ve diğer iade kodları hakkında daha fazla bilgi için [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bakın.

## <a name="remarks"></a>Açıklamalar

**_tell** *işlevi, işleç* bağımsız değişkeniyle ilişkili dosya işaretçisinin (varsa) geçerli konumunu alır. Konum, dosyanın başlangıcından itibaren bayt sayısı olarak ifade edilir. **_telli64** işlevi için bu değer 64 bit tamsayı olarak ifade edilir.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_tell**, **_telli64**|\<io.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

```C
// crt_tell.c
// This program uses _tell to tell the
// file pointer position after a file read.
//

#include <io.h>
#include <stdio.h>
#include <fcntl.h>
#include <share.h>
#include <string.h>

int main( void )
{
   int  fh;
   char buffer[500];

   if ( _sopen_s( &fh, "crt_tell.txt", _O_RDONLY, _SH_DENYNO, 0) )
   {
      char buff[50];
      _strerror_s( buff, sizeof(buff), NULL );
      printf( buff );
      exit( -1 );
   }

   if( _read( fh, buffer, 500 ) > 0 )
      printf( "Current file position is: %d\n", _tell( fh ) );
   _close( fh );
}
```

### <a name="input-crt_telltxt"></a>Giriş: crt_tell.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>Çıktı

```Output
Current file position is: 20
```

## <a name="see-also"></a>Ayrıca bkz.

[Düşük Seviyeli G/Ç](../../c-runtime-library/low-level-i-o.md)<br/>
[ftell, _ftelli64](ftell-ftelli64.md)<br/>
[_lseek, _lseeki64](lseek-lseeki64.md)<br/>
