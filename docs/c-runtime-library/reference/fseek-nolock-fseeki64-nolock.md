---
title: _fseek_nolock, _fseeki64_nolock
ms.date: 4/2/2020
api_name:
- _fseek_nolock
- _fseeki64_nolock
- _o__fseek_nolock
- _o__fseeki64_nolock
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
- _fseek_nolock
- _fseeki64_nolock
- fseek_nolock
- fseeki64_nolock
helpviewer_keywords:
- _fseek_nolock function
- fseeki64_nolock function
- file pointers [C++], moving
- fseek_nolock function
- _fseeki64_nolock function
- seek file pointers
ms.assetid: 2dd4022e-b715-462b-b935-837561605a02
ms.openlocfilehash: 3533e7897e9c460d3be73b8907a6bd3c96f6888f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345730"
---
# <a name="_fseek_nolock-_fseeki64_nolock"></a>_fseek_nolock, _fseeki64_nolock

Dosya işaretçisini belirli bir konuma taşır.

## <a name="syntax"></a>Sözdizimi

```C
int _fseek_nolock(
   FILE *stream,
   long offset,
   int origin
);
int _fseeki64_nolock(
   FILE *stream,
   __int64 offset,
   int origin
);
```

### <a name="parameters"></a>Parametreler

*Akışı*<br/>
**DOSYA** yapısına işaretçi.

*Uzaklık*<br/>
*Kaynaktan*bayt sayısı.

*Kökenli*<br/>
İlk pozisyon.

## <a name="return-value"></a>Dönüş Değeri

Fseek [fseek](fseek-fseeki64.md) ve [_fseeki64](fseek-fseeki64.md)ile aynıdır, sırasıyla.

## <a name="remarks"></a>Açıklamalar

Bu işlevler, sırasıyla [fseek](fseek-fseeki64.md) ve [_fseeki64'nin](fseek-fseeki64.md)kilitlenmeyen sürümleridir. Bunlar, diğer iş parçacıkları tarafından girişime karşı korunmayan lar [dışında, fseek](fseek-fseeki64.md) ve [_fseeki64](fseek-fseeki64.md) ile aynıdır. Bu işlevler, diğer iş parçacıklarını kilitleme ek yüküne tabi olmadığından daha hızlı olabilir. Bu işlevleri yalnızca tek iş parçacığı uygulamaları gibi iş parçacığı güvenli bağlamlarda veya arama kapsamının iş parçacığı yalıtımını zaten işlediği durumlarda kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fseek_nolock**, **_fseeki64_nolock**|\<stdio.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Akış I/O](../../c-runtime-library/stream-i-o.md)<br/>
[ftell, _ftelli64](ftell-ftelli64.md)<br/>
[_lseek, _lseeki64](lseek-lseeki64.md)<br/>
[rewind](rewind.md)<br/>
