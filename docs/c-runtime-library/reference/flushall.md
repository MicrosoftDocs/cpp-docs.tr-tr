---
title: _flushall
ms.date: 4/2/2020
api_name:
- _flushall
- _o__flushall
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
- _flushall
helpviewer_keywords:
- flushall function
- flushing streams
- streams, flushing
- _flushall function
ms.assetid: 2cd73562-6d00-4ca2-b13c-80d0ae7870b5
ms.openlocfilehash: 93181c0fe941a1c5e259e706771495666329bcb3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81346616"
---
# <a name="_flushall"></a>_flushall

Tüm akışları temizler; tüm arabellekleri temizler.

## <a name="syntax"></a>Sözdizimi

```C
int _flushall( void );
```

## <a name="return-value"></a>Dönüş Değeri

**_flushall** açık akış (giriş ve çıkış) sayısını döndürür. Hata iadesi yok.

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, **_flushall** işlevi uygun dosyalara açık çıktı akışları ile ilişkili tüm arabelleklerin içeriğini yazar. Açık giriş akışlarıyla ilişkili tüm arabellekler geçerli içeriklerinden temizlenir. (Bu arabellekler normalde, verileri diske otomatik olarak yazmak için en uygun zamanı belirleyen işletim sistemi tarafından korunur: arabellek dolduğunda, bir akış kapatıldığında veya bir program akışları kapatmadan normal olarak sona erdiğinde.)

Bir okuma **_flushall**için bir çağrı izler, yeni veri arabellekleri içine giriş dosyalarından okunur. tüm akışlar **_flushall'a**yapılan çağrıdan sonra açık kalır.

Çalışma zamanı kitaplığı'nın diske işleme özelliği, kritik verilerin işletim sistemi arabelleklerine değil, doğrudan diske yazılmasını sağlamanızı sağlar. Varolan bir programı yeniden yazmadan, programın nesne dosyalarını Commode.obj ile bağlayarak bu özelliği etkinleştirebilirsiniz. Ortaya çıkan yürütülebilir dosyada, tüm arabelleklerin içeriğini diske yazmak **_flushall** için yapılan çağrılar. Commode.obj sadece **_flushall** ve [fflush](fflush.md) etkilenir.

Commit-to-disk özelliğini denetleme hakkında bilgi için [Bkz. Stream G/Ç](../../c-runtime-library/stream-i-o.md), [fopen](fopen-wfopen.md)ve [_fdopen.](fdopen-wfdopen.md)

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_flushall**|\<stdio.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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

[Akış I/O](../../c-runtime-library/stream-i-o.md)<br/>
[_commit](commit.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[fflush](fflush.md)<br/>
[setvbuf](setvbuf.md)<br/>
