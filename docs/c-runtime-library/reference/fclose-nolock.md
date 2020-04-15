---
title: _fclose_nolock
ms.date: 4/2/2020
api_name:
- _fclose_nolock
- _o__fclose_nolock
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
- fclose_nolock
- _fclose_nolock
helpviewer_keywords:
- streams, closing
- fclose_nolock function
- _fclose_nolock function
ms.assetid: b4af4392-5fc8-49bb-9fe2-ca7293d3ce04
ms.openlocfilehash: 5ec1db740ae27bca81237bda43d47d51576243f1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81347470"
---
# <a name="_fclose_nolock"></a>_fclose_nolock

İş parçacığı kilitlemeden akışı kapatır.

## <a name="syntax"></a>Sözdizimi

```C
int _fclose_nolock(
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*Akışı*<br/>
**DOSYA** yapısına işaretçi.

## <a name="return-value"></a>Dönüş Değeri

akış başarıyla kapatılırsa **fclose** 0 döndürür. Bir hata belirtmek için **EOF'yi** döndürür.

## <a name="remarks"></a>Açıklamalar

Bu işlevler **fclose**olmayan bir kilitleme sürümüdür. Diğer iş parçacıkları tarafından girişime karşı korumalı olmaması dışında aynıdır. Diğer iş parçacığı kilitleme yükü ne bilgili değildir, çünkü daha hızlı olabilir. Bu işlevi yalnızca tek iş parçacığı uygulamaları gibi iş parçacığı güvenli bağlamlarda veya arama kapsamının iş parçacığı yalıtımını zaten işlediği durumlarda kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fclose_nolock**|\<stdio.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Akış I/O](../../c-runtime-library/stream-i-o.md)<br/>
[_close](close.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[fflush](fflush.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[freopen, _wfreopen](freopen-wfreopen.md)<br/>
