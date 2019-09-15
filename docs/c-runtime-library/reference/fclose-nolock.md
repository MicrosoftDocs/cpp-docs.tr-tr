---
title: _fclose_nolock
ms.date: 11/04/2016
api_name:
- _fclose_nolock
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
- fclose_nolock
- _fclose_nolock
helpviewer_keywords:
- streams, closing
- fclose_nolock function
- _fclose_nolock function
ms.assetid: b4af4392-5fc8-49bb-9fe2-ca7293d3ce04
ms.openlocfilehash: 2e19604f09cdb3ac2a5bfc1635c2b98a8d5218c5
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70941422"
---
# <a name="_fclose_nolock"></a>_fclose_nolock

İş parçacığı kilitleme olmadan bir akışı kapatır.

## <a name="syntax"></a>Sözdizimi

```C
int _fclose_nolock(
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*ka*<br/>
**Dosya** yapısına yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Akış başarıyla kapatılırsa, **fclose** 0 döndürür. Bir hatayı göstermek için **EOF** döndürür.

## <a name="remarks"></a>Açıklamalar

Bu işlevler, **fclose**'un kilitleme dışı bir sürümüdür. Bu, diğer iş parçacıklarının girişim tarafından korunmamasının dışında aynıdır. Diğer iş parçacıklarını kilitleme yükünü karşılamadığından daha hızlı olabilir. Bu işlevi yalnızca tek iş parçacıklı uygulamalar gibi iş parçacığı güvenli bağlamlarda veya çağırma kapsamının iş parçacığı yalıtımını zaten işlediği yerde kullanın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fclose_nolock**|\<stdio. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[_close](close.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[fflush](fflush.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[freopen, _wfreopen](freopen-wfreopen.md)<br/>
