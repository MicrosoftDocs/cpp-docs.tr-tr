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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 1a53eeedd5dfa0f9c01fa5883a9db33e26e3ea17
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82911618"
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

Varsayılan olarak **_flushall** işlevi, açık çıkış akışlarıyla ilişkili tüm arabelleklerin içeriğini uygun dosyalara yazar. Açık giriş akışlarıyla ilişkili tüm arabellekler geçerli içeriklerinin işaretini temizlemez. (Bu arabellekler normalde işletim sistemi tarafından korunur. Bu, verilerin diske otomatik olarak yazılması için en iyi zamanı belirler: bir arabellek dolduğunda, bir akış kapatıldığında veya bir program normal olarak akışları kapatmadan sonlandırıldığında.)

Bir okuma **_flushall**bir çağrıyı izliyorsa, yeni veriler giriş dosyalarından arabelleklere okundu. **_Flushall**çağrısından sonra tüm akışlar açık kalır.

Çalışma zamanı kitaplığının diske kaydet özelliği, kritik verilerin işletim sistemi arabellekleri yerine doğrudan diske yazılmasını sağlamanıza olanak tanır. Mevcut bir programı yeniden yazmadan, programın nesne dosyalarını Commode. obj ile bağlayarak bu özelliği etkinleştirebilirsiniz. Elde edilen yürütülebilir dosyada, tüm arabelleklerin içeriğini diske yazmak **_flushall** için çağırır. Yalnızca **_flushall** ve [fflush](fflush.md) , Commode. obj tarafından etkilendi.

Diske işleme özelliğini denetleme hakkında daha fazla bilgi için bkz. [akış g/ç](../../c-runtime-library/stream-i-o.md), [fopen](fopen-wfopen.md)ve [_fdopen](fdopen-wfdopen.md).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_flushall**|\<stdio. h>|

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
