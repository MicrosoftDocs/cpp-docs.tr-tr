---
title: _ftell_nolock, _ftelli64_nolock
ms.date: 11/04/2016
apiname:
- _ftelli64_nolock
- _ftell_nolock
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
ms.openlocfilehash: 58bfc8c7a8b8e820fdec09d52e24dfcb07f328f8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62332942"
---
# <a name="ftellnolock-ftelli64nolock"></a>_ftell_nolock, _ftelli64_nolock

İş parçacığını kilitlemeden, bir dosya işaretçisiyse, geçerli konumunu alır.

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

*Stream*<br/>
Hedef **dosya** yapısı.

## <a name="return-value"></a>Dönüş Değeri

Aynı **ftell** ve **_ftelli64**. Daha fazla bilgi için [ftell, _ftelli64](ftell-ftelli64.md).

## <a name="remarks"></a>Açıklamalar

Kilitleme olmayan bu işlevlerin sürümleri **ftell** ve **_ftelli64**sırasıyla. Bunlar aynı olan **ftell** ve **_ftelli64** hariç, bunlar başka iş parçacıklarının engellemelerinden korunmamaları. Bu işlevler, diğer iş parçacıklarını kilitleme ek yükü kalmadıklarından daha hızlı olabilir. Bu işlevler yalnızca tek iş parçacıklı uygulamalar ve burada çağırma kapsamının iş parçacığı yalıtımını zaten işlediği gibi iş parçacığı bakımından güvenli bağlamlarda kullanın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|İsteğe bağlı başlık|
|--------------|---------------------|---------------------|
|**ftell_nolock**|\<stdio.h >|\<errno.h >|
|**_ftelli64_nolock**|\<stdio.h >|\<errno.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fgetpos](fgetpos.md)<br/>
[fseek, _fseeki64](fseek-fseeki64.md)<br/>
[_lseek, _lseeki64](lseek-lseeki64.md)<br/>
[ftell, _ftelli64](ftell-ftelli64.md)<br/>
