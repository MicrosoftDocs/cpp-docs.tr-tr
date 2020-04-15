---
title: _fflush_nolock
ms.date: 4/2/2020
api_name:
- _fflush_nolock
- _o__fflush_nolock
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
- fflush_nolock
- _fflush_nolock
helpviewer_keywords:
- fflush_nolock function
- _fflush_nolock function
- streams, flushing
- flushing
ms.assetid: 5e33c4a1-b10c-4001-ad01-210757919291
ms.openlocfilehash: 0ee61ffe6b9aabb4a8bffb803c492905d45a5374
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81347235"
---
# <a name="_fflush_nolock"></a>_fflush_nolock

İş parçacığı kilitlemeden bir akışı temizler.

## <a name="syntax"></a>Sözdizimi

```C
int _fflush_nolock(
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*Akışı*<br/>
**DOSYA** yapısına işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Bkz. [fflush](fflush.md).

## <a name="remarks"></a>Açıklamalar

Bu işlev **fflush**olmayan bir kilitleme sürümüdür. Diğer iş parçacıkları tarafından girişime karşı korumalı olmaması dışında **fflush** ile aynıdır. Diğer iş parçacığı kilitleme yükü ne bilgili değildir, çünkü daha hızlı olabilir. Bu işlevi yalnızca tek iş parçacığı uygulamaları gibi iş parçacığı güvenli bağlamlarda veya arama kapsamının iş parçacığı yalıtımını zaten işlediği durumlarda kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fflush_nolock**|\<stdio.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Akış I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[_flushall](flushall.md)<br/>
[setvbuf](setvbuf.md)<br/>
