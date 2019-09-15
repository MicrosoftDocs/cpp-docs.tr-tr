---
title: _fileno
ms.date: 11/04/2016
api_name:
- _fileno
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
- _fileno
helpviewer_keywords:
- file handles [C++], getting from streams
- fileno function
- _fileno function
- streams, getting file handles
ms.assetid: 86474174-2f17-4100-bcc4-352dd976c7b5
ms.openlocfilehash: 586e390e100f5dc46a49b99c007016cf23ac68f0
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957213"
---
# <a name="_fileno"></a>_fileno

Bir akışla ilişkili dosya tanımlayıcısını alır.

## <a name="syntax"></a>Sözdizimi

```C
int _fileno(
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*ka*<br/>
**Dosya** yapısına yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

**_fileno** , dosya tanımlayıcısını döndürür. Hata döndürme yok. *Akış* bir açık dosya belirtmezse sonuç tanımsızdır. Stream **null**ise, **_Fileno** [parametresi, parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, bu işlev-1 döndürür ve **errno** 'ı **EINVAL**olarak ayarlar.

Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

> [!NOTE]
> **Stdout** veya **stderr** bir çıkış akışı ile ilişkili değilse (örneğin, konsol penceresi olmayan bir Windows uygulamasında), döndürülen dosya tanımlayıcısı-2 ' dir. Önceki sürümlerde, döndürülen dosya tanımlayıcısı-1 idi. Bu değişiklik, uygulamaların bu durumu bir hatadan ayırt etmesine olanak tanır.

## <a name="remarks"></a>Açıklamalar

**_Fileno** yordamı, şu anda *Stream*ile ilişkili olan dosya tanımlayıcısını döndürür. Bu yordam, hem işlev hem de makro olarak uygulanır. Uygulama seçme hakkında daha fazla bilgi için bkz. [işlevler ve makrolar arasında seçim yapma](../../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fileno**|\<stdio. h >|

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

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[_filelength, _filelengthi64](filelength-filelengthi64.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[freopen, _wfreopen](freopen-wfreopen.md)<br/>
