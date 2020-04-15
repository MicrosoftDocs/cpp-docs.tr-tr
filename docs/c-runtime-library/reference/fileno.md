---
title: _fileno
ms.date: 4/2/2020
api_name:
- _fileno
- _o__fileno
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
- _fileno
helpviewer_keywords:
- file handles [C++], getting from streams
- fileno function
- _fileno function
- streams, getting file handles
ms.assetid: 86474174-2f17-4100-bcc4-352dd976c7b5
ms.openlocfilehash: ec4f08e499efe82b0ee35235e6e2d86dbb9bab66
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81346838"
---
# <a name="_fileno"></a>_fileno

Dosya tanımlayıcısını bir akışla ilişkilendiren alır.

## <a name="syntax"></a>Sözdizimi

```C
int _fileno(
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*Akışı*<br/>
**DOSYA** yapısına işaretçi.

## <a name="return-value"></a>Dönüş Değeri

**_fileno** dosya tanımlayıcısını döndürür. Hata iadesi yok. *Akış* açık bir dosya belirtmiyorsa sonuç tanımsızdır. Akış **NULL**ise, **_fileno** [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmedevam etmesine izin verilirse, bu işlev -1 döndürür ve **EINVAL** **için errno** ayarlar.

Bu ve diğer hata kodları hakkında daha fazla bilgi için [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)bakın.

> [!NOTE]
> **Stdout** veya **stderr** bir çıktı akışıyla ilişkili değilse (örneğin, konsol penceresi olmayan bir Windows uygulamasında), döndürülen dosya tanımlayıcısı -2'dir. Önceki sürümlerde, dosya tanımlayıcısı -1 idi. Bu değişiklik, uygulamaların bu durumu bir hatadan ayırt etmesine olanak tanır.

## <a name="remarks"></a>Açıklamalar

**yordamı _fileno,** şu anda *akışla*ilişkili dosya tanımlayıcısını döndürür. Bu yordam hem işlev hem de makro olarak uygulanır. Her iki uygulamayı seçme hakkında bilgi için [bkz.](../../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md)

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fileno**|\<stdio.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

```C
// crt_fileno.c
// This program uses _fileno to obtain
// the file descriptor for some standard C streams.
//

#include <stdio.h>

int main( void )
{
   printf( "The file descriptor for stdin is %d\n", _fileno( stdin ) );
   printf( "The file descriptor for stdout is %d\n", _fileno( stdout ) );
   printf( "The file descriptor for stderr is %d\n", _fileno( stderr ) );
}
```

```Output
The file descriptor for stdin is 0
The file descriptor for stdout is 1
The file descriptor for stderr is 2
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış I/O](../../c-runtime-library/stream-i-o.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[_filelength, _filelengthi64](filelength-filelengthi64.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[freopen, _wfreopen](freopen-wfreopen.md)<br/>
