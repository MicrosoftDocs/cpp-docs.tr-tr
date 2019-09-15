---
title: _ftell_nolock, _ftelli64_nolock
ms.date: 11/04/2016
api_name:
- _ftelli64_nolock
- _ftell_nolock
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
- _ftelli64_nolock
- ftelli64_nolock
- ftell_nolock
- _ftell_nolock
helpviewer_keywords:
- ftelli64_nolock function
- _ftelli64_nolock function
- _ftell_nolock function
- ftell_nolock function
- file pointers [C++], getting current position
ms.assetid: 84e68b0a-32f8-4c4a-90ad-3f2387685ede
ms.openlocfilehash: 9e72687077cc5401bb411fca81a3ccec48a6258f
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70956361"
---
# <a name="_ftell_nolock-_ftelli64_nolock"></a>_ftell_nolock, _ftelli64_nolock

İş parçacığını kilitlemeden bir dosya işaretçisinin geçerli konumunu alır.

## <a name="syntax"></a>Sözdizimi

```C
long _ftell_nolock(
   FILE *stream
);
__int64 _ftelli64_nolock(
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*ka*<br/>
**Dosya** yapısını hedefleyin.

## <a name="return-value"></a>Dönüş Değeri

**Fsöyleyin** ve **_ftelli64**ile aynı. Daha fazla bilgi için bkz. [fsöyleyin, _ftelli64](ftell-ftelli64.md).

## <a name="remarks"></a>Açıklamalar

Bu işlevler sırasıyla **fsöyleyin** ve **_ftelli64**'in kilitleme dışı sürümleridir. Bunlar, diğer iş parçacıkları tarafından girişime karşı korunmamaları hariç **fsöyleyin** ve **_ftelli64** ile aynıdır. Bu işlevler, diğer iş parçacıklarını kilitleme yükünü ortadan bulmadığından daha hızlı olabilir. Bu işlevleri yalnızca, tek iş parçacıklı uygulamalar gibi iş parçacığı güvenli bağlamlarda veya çağırma kapsamının iş parçacığı yalıtımını zaten işlediği yerde kullanın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|İsteğe bağlı başlık|
|--------------|---------------------|---------------------|
|**ftell_nolock**|\<stdio. h >|\<errno. h >|
|**_ftelli64_nolock**|\<stdio. h >|\<errno. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fgetpos](fgetpos.md)<br/>
[fseek, _fseeki64](fseek-fseeki64.md)<br/>
[_lseek, _lseeki64](lseek-lseeki64.md)<br/>
[ftell, _ftelli64](ftell-ftelli64.md)<br/>
