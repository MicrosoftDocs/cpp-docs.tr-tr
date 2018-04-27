---
title: _ftell_nolock, _ftelli64_nolock | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- ftelli64_nolock function
- _ftelli64_nolock function
- _ftell_nolock function
- ftell_nolock function
- file pointers [C++], getting current position
ms.assetid: 84e68b0a-32f8-4c4a-90ad-3f2387685ede
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f00920fbb262cd564ce0ac6bc454d3ef560c6941
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="ftellnolock-ftelli64nolock"></a>_ftell_nolock, _ftelli64_nolock

İş parçacığı kilitlemeden dosya işaretçisini geçerli konumunu alır.

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

*Akış*<br/>
Hedef **dosya** yapısı.

## <a name="return-value"></a>Dönüş Değeri

Aynı **ftell** ve **_ftelli64**. Daha fazla bilgi için bkz: [ftell, _ftelli64](ftell-ftelli64.md).

## <a name="remarks"></a>Açıklamalar

Bu işlevler kilitleme olmayan sürümleri **ftell** ve **_ftelli64**sırasıyla. Aynı **ftell** ve **_ftelli64** dışında diğer iş parçacıkları tarafından girişime korunmaz. Bunlar başka bir iş parçacığı kilitleme zahmetine değil çünkü bu işlevler daha hızlı olabilir. Bu işlevler yalnızca iş parçacığı bağlamları tek iş parçacıklı uygulamalar veya arama kapsamı zaten iş parçacığı yalıtım işleme olduğu gibi kullanın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|İsteğe bağlı üstbilgi|
|--------------|---------------------|---------------------|
|**ftell_nolock**|\<stdio.h >|\<errno.h >|
|**_ftelli64_nolock**|\<stdio.h >|\<errno.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fgetpos](fgetpos.md)<br/>
[fseek, _fseeki64](fseek-fseeki64.md)<br/>
[_lseek, _lseeki64](lseek-lseeki64.md)<br/>
[ftell, _ftelli64](ftell-ftelli64.md)<br/>
