---
title: _fread_nolock
ms.date: 4/2/2020
api_name:
- _fread_nolock
- _o__fread_nolock
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
- _fread_nolock
- fread_nolock
helpviewer_keywords:
- reading data [C++], from input streams
- data [C++], reading from input stream
- fread_nolock function
- _fread_nolock function
- streams [C++], reading data from
ms.assetid: 60e4958b-1097-46f5-a77b-94af5e7dba40
ms.openlocfilehash: 97b37b4fee85a827faa4b309741afe56d8d0cbb9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81346103"
---
# <a name="_fread_nolock"></a>_fread_nolock

Diğer iş parçacıklarını kilitlemeden bir akıştan gelen verileri okur.

## <a name="syntax"></a>Sözdizimi

```C
size_t _fread_nolock(
   void *buffer,
   size_t size,
   size_t count,
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*Arabellek*<br/>
Veriler için depolama konumu.

*Boyutu*<br/>
Baytlarda madde boyutu.

*Sayısı*<br/>
Okunacak maksimum öğe sayısı.

*Akışı*<br/>
**DOSYA** yapısına işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Bkz. [fread](fread.md).

## <a name="remarks"></a>Açıklamalar

Bu **işlev, fread'in**kilitlenmeyen bir sürümüdür. Diğer iş parçacıkları tarafından girişimden korunmadığı **dışında, fread** ile aynıdır. Diğer iş parçacığı kilitleme yükü ne bilgili değildir, çünkü daha hızlı olabilir. Bu işlevi yalnızca tek iş parçacığı uygulamaları gibi iş parçacığı güvenli bağlamlarda veya arama kapsamının iş parçacığı yalıtımını zaten işlediği durumlarda kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fread_nolock**|\<stdio.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Akış I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fwrite](fwrite.md)<br/>
[_read](read.md)<br/>
