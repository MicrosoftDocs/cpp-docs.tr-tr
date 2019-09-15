---
title: _flushall
ms.date: 11/04/2016
api_name:
- _flushall
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
- _flushall
helpviewer_keywords:
- flushall function
- flushing streams
- streams, flushing
- _flushall function
ms.assetid: 2cd73562-6d00-4ca2-b13c-80d0ae7870b5
ms.openlocfilehash: dce7412ccc19d4870494851d366c059ff01de16a
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957147"
---
# <a name="_flushall"></a>_flushall

Tüm akışları temizler; Tüm arabellekleri temizler.

## <a name="syntax"></a>Sözdizimi

```C
int _flushall( void );
```

## <a name="return-value"></a>Dönüş Değeri

**_flushall** , açık akışlar (giriş ve çıkış) sayısını döndürür. Hata döndürme yok.

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, **_flushall** işlevi, açık çıkış akışlarıyla ilişkili tüm arabelleklerin içeriğini uygun dosyalara yazar. Açık giriş akışlarıyla ilişkili tüm arabellekler geçerli içeriklerinin işaretini temizlemez. (Bu arabellekler normalde işletim sistemi tarafından korunur. Bu, verilerin diske otomatik olarak yazılması için en iyi zamanı belirler: bir arabellek dolduğunda, bir akış kapatıldığında veya bir program normal olarak akışları kapatmadan sonlandırıldığında.)

Bir okuma **_flushall**öğesine yapılan bir çağrıyı izliyorsa, yeni veriler giriş dosyalarından arabelleklere okundu. Tüm akışlar **_flushall**çağrısından sonra açık kalır.

Çalışma zamanı kitaplığının diske kaydet özelliği, kritik verilerin işletim sistemi arabellekleri yerine doğrudan diske yazılmasını sağlamanıza olanak tanır. Mevcut bir programı yeniden yazmadan, programın nesne dosyalarını Commode. obj ile bağlayarak bu özelliği etkinleştirebilirsiniz. Elde edilen yürütülebilir dosyada, **_flushall** çağrılarına tüm arabelleklerin içeriğini diske yazar. Yalnızca **_flushall** ve [fflush](fflush.md) , Commode. obj tarafından etkilendi.

Diske işleme özelliğini denetleme hakkında daha fazla bilgi için bkz. [Stream g/ç](../../c-runtime-library/stream-i-o.md), [fopen](fopen-wfopen.md)ve [_fdopen](fdopen-wfdopen.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_flushall**|\<stdio. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_flushall.c
// This program uses _flushall
// to flush all open buffers.

#include <stdio.h>

int main( void )
{
   int numflushed;

   numflushed = _flushall();
   printf( "There were %d streams flushed\n", numflushed );
}
```

```Output
There were 3 streams flushed
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[_commit](commit.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[fflush](fflush.md)<br/>
[setvbuf](setvbuf.md)<br/>
