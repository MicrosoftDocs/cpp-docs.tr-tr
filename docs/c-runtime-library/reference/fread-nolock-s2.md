---
title: _fread_nolock_s2
ms.date: 4/2/2020
api_name:
- _fread_nolock_s
- _o__fread_nolock_s
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
- _fread_nolock_s
- stdio/_fread_nolock_s
ms.assetid: 5badb9ab-11df-4e17-8162-30bda2a4572e
ms.openlocfilehash: 3fb34a75a0281058a1d70ce41e1ce33b4b1bbb59
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81346143"
---
# <a name="_fread_nolock_s"></a>_fread_nolock_s

Diğer iş parçacıklarını kilitlemeden bir akıştan gelen verileri okur. [fread_nolock](fread-nolock.md) bu sürümü, [CRT'deki Güvenlik Özellikleri'nde](../../c-runtime-library/security-features-in-the-crt.md)açıklandığı gibi güvenlik geliştirmelerine sahiptir.

## <a name="syntax"></a>Sözdizimi

```C
size_t _fread_nolock_s(
   void *buffer,
   size_t bufferSize,
   size_t elementSize,
   size_t elementCount,
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*Arabellek*<br/>
Veriler için depolama konumu.

*Buffersize*<br/>
Baytlar'daki hedef arabelleği boyutu.

*elementBoyut*<br/>
Baytokunacak öğenin boyutu.

*elementCount*<br/>
Okunacak maksimum öğe sayısı.

*Akışı*<br/>
**DOSYA** yapısı için işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Bkz. [fread_s](fread-s.md).

## <a name="remarks"></a>Açıklamalar

Bu **işlev, fread_s**kilitlenmeyen bir sürümüdür. Diğer iş parçacıkları tarafından girişime karşı korumalı olmaması dışında **fread_s** ile aynıdır. Diğer iş parçacığı kilitleme yükü ne bilgili değildir, çünkü daha hızlı olabilir. Bu işlevi yalnızca tek iş parçacığı uygulamaları gibi iş parçacığı güvenli bağlamlarda veya arama kapsamının iş parçacığı yalıtımını zaten işlediği durumlarda kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fread_nolock_s**|C: \<stdio.h>; C++: \<cstdio \<> veya stdio.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Akış I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fwrite](fwrite.md)<br/>
[_read](read.md)<br/>
