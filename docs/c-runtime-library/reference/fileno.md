---
title: _fileno
ms.date: 11/04/2016
apiname:
- _fileno
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
- _fileno
helpviewer_keywords:
- file handles [C++], getting from streams
- fileno function
- _fileno function
- streams, getting file handles
ms.assetid: 86474174-2f17-4100-bcc4-352dd976c7b5
ms.openlocfilehash: 682ab4b01a663bd9a6314138aa692b1c05b7437a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62333774"
---
# <a name="fileno"></a>_fileno

Bir akış ile ilişkili dosya tanımlayıcısını alır.

## <a name="syntax"></a>Sözdizimi

```C
int _fileno(
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*Stream*<br/>
İşaretçi **dosya** yapısı.

## <a name="return-value"></a>Dönüş Değeri

**_fileno** dosya tanımlayıcısını döndürür. Döndürülen hata yok. Varsa sonuç tanımsızdır *stream* açık bir dosyayı belirtmiyor. Akış ise **NULL**, **_fileno** açıklandığı gibi geçersiz parametre işleyicisini çağırır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Devam etmek için bu işlev -1 döndürür ve kümeleri yürütülmesine izin veriliyorsa **errno** için **EINVAL**.

Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

> [!NOTE]
> Varsa **stdout** veya **stderr** ilişkili değil (örneğin, bir konsol penceresi olmadan bir Windows uygulaması) bir çıkış akışı ile döndürülen dosya -2 tanımlayıcısıdır. Önceki sürümlerde, -1 döndürülen dosya tanımlayıcısı oluştu. Bu değişiklik, bu durum bir hata ayırt etmek uygulamalar sağlar.

## <a name="remarks"></a>Açıklamalar

**_Fileno** yordamı şu anda ilişkili dosya tanımlayıcısı döndürür *stream*. Bu yordam, hem bir işlev ve makro olarak uygulanmıştır. Uygulamayı seçme hakkında daha fazla bilgi için bkz: [seçme arasında işlevlerle makrolar](../../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fileno**|\<stdio.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[_filelength, _filelengthi64](filelength-filelengthi64.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[freopen, _wfreopen](freopen-wfreopen.md)<br/>
