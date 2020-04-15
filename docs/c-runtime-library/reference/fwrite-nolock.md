---
title: _fwrite_nolock
ms.date: 4/2/2020
api_name:
- _fwrite_nolock
- _o__fwrite_nolock
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
- _fwrite_nolock
- fwrite_nolock
helpviewer_keywords:
- fwrite_nolock function
- streams, writing data to
- _fwrite_nolock function
ms.assetid: 2b4ec6ce-742e-4615-8407-44a0a18ec1d7
ms.openlocfilehash: 9623606cb79dc4c0ac988960545faf3d91c42f9d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345451"
---
# <a name="_fwrite_nolock"></a>_fwrite_nolock

İş parçacığı kilitlemeden bir akışa veri yazar.

## <a name="syntax"></a>Sözdizimi

```C
size_t _fwrite_nolock(
   const void *buffer,
   size_t size,
   size_t count,
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*Arabellek*<br/>
Yazılacak verileri işaretçi.

*Boyutu*<br/>
Baytlarda madde boyutu.

*Sayısı*<br/>
Yazılacak maksimum öğe sayısı.

*Akışı*<br/>
**DOSYA** yapısına işaretçi.

## <a name="return-value"></a>Dönüş Değeri

[Fwrite](fwrite.md)ile aynı.

## <a name="remarks"></a>Açıklamalar

Bu işlev **fwrite**olmayan bir kilitleme sürümüdür. Diğer iş parçacıkları tarafından girişimden korunmadığı dışında **fwrite** ile aynıdır. Diğer iş parçacığı kilitleme yükü ne bilgili değildir, çünkü daha hızlı olabilir. Bu işlevi yalnızca tek iş parçacığı uygulamaları gibi iş parçacığı güvenli bağlamlarda veya arama kapsamının iş parçacığı yalıtımını zaten işlediği durumlarda kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fwrite_nolock**|\<stdio.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

[Fread](fread.md)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Akış I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fread](fread.md)<br/>
[_write](write.md)<br/>
