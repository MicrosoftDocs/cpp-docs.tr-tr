---
title: _flushall
ms.date: 11/04/2016
apiname:
- _flushall
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
- _flushall
helpviewer_keywords:
- flushall function
- flushing streams
- streams, flushing
- _flushall function
ms.assetid: 2cd73562-6d00-4ca2-b13c-80d0ae7870b5
ms.openlocfilehash: de8caf30568816f41441f5d9487293c346d2bff1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62333540"
---
# <a name="flushall"></a>_flushall

Tüm akışları aktarır; Tüm arabellekler temizler.

## <a name="syntax"></a>Sözdizimi

```C
int _flushall( void );
```

## <a name="return-value"></a>Dönüş Değeri

**_flushall** açık akış (girdi ve çıktı) sayısını döndürür. Döndürülen hata yok.

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, **_flushall** için yazar uygun dosya açık çıkış akışları ile ilişkili tüm arabellekler içeriğini işlevi. Açık giriş akışları ile ilişkili tüm arabellekler kendi geçerli içeriğini temizlenir. (Bu arabellekleri normalde verileri otomatik olarak diske yazmak için en iyi zamanı belirler işletim sistemi tarafından korunur: Arabellek dolduğunda, bir akış kapatıldığında veya ne zaman bir program akışları kapatmadan sona erer.)

Okuma çağrısı izliyorsa **_flushall**, yeni veri arabellekler giriş dosyalarından okuma. Tüm akışlar, çağrısından sonra açık kalması **_flushall**.

Çalışma zamanı kitaplığının işleme disk özellik kritik verileri doğrudan disk yerine işletim sistemi arabelleklerini yazıldığından emin olanak sağlar. Varolan bir program yeniden yazma olmadan programın nesne dosyaları Commode.obj ile bağlayarak bu özelliği etkinleştirebilirsiniz. Oluşturulan yürütülebilir dosya olarak çağrılar **_flushall** arabelleklerin içeriğini diske yazma. Yalnızca **_flushall** ve [fflush](fflush.md) Commode.obj tarafından etkilenir.

Yürütme disk özellik denetleme hakkında daha fazla bilgi için bkz [Stream g/ç](../../c-runtime-library/stream-i-o.md), [fopen](fopen-wfopen.md), ve [_fdopen](fdopen-wfdopen.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_flushall**|\<stdio.h >|

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

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[_commit](commit.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[fflush](fflush.md)<br/>
[setvbuf](setvbuf.md)<br/>
