---
description: 'Hakkında daha fazla bilgi edinin: _fclose_nolock'
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: aa7c12080838ab07dc0eb184413bb27089d9ee06
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97235898"
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

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fclose_nolock**|\<stdio.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Akış G/Ç](../../c-runtime-library/stream-i-o.md)<br/>
[_close](close.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[fflush](fflush.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[freopen, _wfreopen](freopen-wfreopen.md)<br/>
