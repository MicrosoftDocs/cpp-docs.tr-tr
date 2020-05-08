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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: c09f9964416785131c0c928c214a0de5ec6dd859
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82910167"
---
# <a name="_fseek_nolock-_fseeki64_nolock"></a>_fseek_nolock, _fseeki64_nolock

Dosya işaretçisini belirtilen konuma kaydırır.

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

*ka*<br/>
**Dosya** yapısına yönelik işaretçi.

*konumu*<br/>
*Kaynaktan*gelen bayt sayısı.

*tıdır*<br/>
Başlangıç konumu.

## <a name="return-value"></a>Dönüş Değeri

Sırasıyla [fseek](fseek-fseeki64.md) ve [_fseeki64](fseek-fseeki64.md)ile aynıdır.

## <a name="remarks"></a>Açıklamalar

Bu işlevler, sırasıyla [fseek](fseek-fseeki64.md) ve [_fseeki64](fseek-fseeki64.md)'nin kilitleme dışı sürümleridir. Bunlar, diğer iş parçacıkları tarafından girişime karşı korunmamaları dışında, [fseek](fseek-fseeki64.md) ve [_fseeki64](fseek-fseeki64.md) aynıdır. Bu işlevler, diğer iş parçacıklarını kilitleme yükünü ortadan bulmadığından daha hızlı olabilir. Bu işlevleri yalnızca, tek iş parçacıklı uygulamalar gibi iş parçacığı güvenli bağlamlarda veya çağırma kapsamının iş parçacığı yalıtımını zaten işlediği yerde kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fseek_nolock**, **_fseeki64_nolock**|\<stdio. h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[ftell, _ftelli64](ftell-ftelli64.md)<br/>
[_lseek, _lseeki64](lseek-lseeki64.md)<br/>
[rewind](rewind.md)<br/>
