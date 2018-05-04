---
title: _flushall | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- flushall function
- flushing streams
- streams, flushing
- _flushall function
ms.assetid: 2cd73562-6d00-4ca2-b13c-80d0ae7870b5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7fb094e2f99e0554320df69946470f42f461819d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="flushall"></a>_flushall

Tüm akışlar aktarır; Tüm arabellekler temizler.

## <a name="syntax"></a>Sözdizimi

```C
int _flushall( void );
```

## <a name="return-value"></a>Dönüş Değeri

**_flushall** açık akış (girdi ve çıktı) sayısını döndürür. Döndürülen hata yoktur.

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, **_flushall** için yazar uygun dosyaları açık çıkış akışları ile ilişkili tüm arabelleklerinin içeriğini işlevi. Açık giriş akışları ile ilişkili tüm arabellekler kendi geçerli içeriğini temizlenir. (Bu arabellekleri normalde verileri otomatik olarak diske yazmak için en iyi zamanı belirler işletim sistemi tarafından korunur: bir arabellek dolduğunda, bir akış kapalıyken veya ne zaman bir program akışları kapatmadan sona erer.)

Okuma yapılan bir çağrı izliyorsa **_flushall**, yeni verileri arabellekleri giriş dosyalarından okuyun. Çağrısından sonra tüm akışlar açık kalmaya **_flushall**.

Çalışma Zamanı Kitaplığı commit-to-disk özellik kritik verileri doğrudan diske yerine işletim sistemi arabellekleri için yazılmış emin olun olanak sağlar. Varolan bir programı'nı yeniden yazma işlemi olmadan, programın nesne dosyaları Commode.obj ile bağlayarak bu özelliği etkinleştirebilirsiniz. Sonuçta elde edilen yürütülebilir dosyada çağrılar **_flushall** tüm arabelleklerinin içeriğini diske yazma. Yalnızca **_flushall** ve [fflush](fflush.md) Commode.obj tarafından etkilenir.

Commit-to-disk özelliği denetleme hakkında daha fazla bilgi için bkz: [akış g/ç](../../c-runtime-library/stream-i-o.md), [fopen](fopen-wfopen.md), ve [_fdopen](fdopen-wfdopen.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_flushall**|\<stdio.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
