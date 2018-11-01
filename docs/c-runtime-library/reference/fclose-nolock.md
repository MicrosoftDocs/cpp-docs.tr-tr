---
title: _fclose_nolock
ms.date: 11/04/2016
apiname:
- _fclose_nolock
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
- fclose_nolock
- _fclose_nolock
helpviewer_keywords:
- streams, closing
- fclose_nolock function
- _fclose_nolock function
ms.assetid: b4af4392-5fc8-49bb-9fe2-ca7293d3ce04
ms.openlocfilehash: 440582bb42a1795721eab17b24be3e0bc3daf80f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50620967"
---
# <a name="fclosenolock"></a>_fclose_nolock

İş parçacığı kilitleme olmadan bir akışı kapatır.

## <a name="syntax"></a>Sözdizimi

```C
int _fclose_nolock(
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*Stream*<br/>
İşaretçi **dosya** yapısı.

## <a name="return-value"></a>Dönüş Değeri

**fclose** akışın başarılı bir şekilde kapanırsa, 0 döndürür. Döndürür **EOF** bir hatayı göstermek için.

## <a name="remarks"></a>Açıklamalar

Bu işlevler, kilitleme yapılmayan bir sürümünü **fclose**. Bunu başka iş parçacıklarının engellemelerinden korunmamaları hariç, aynıdır. Diğer iş parçacıklarının kilitleme yüküne tabi olmayan çünkü daha hızlı olabilir. Bu işlev yalnızca tek iş parçacıklı uygulamalar ve burada çağırma kapsamının iş parçacığı yalıtımını zaten işlediği gibi iş parçacığı bakımından güvenli bağlamlarda kullanın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fclose_nolock**|\<stdio.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[_close](close.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[fflush](fflush.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[freopen, _wfreopen](freopen-wfreopen.md)<br/>
