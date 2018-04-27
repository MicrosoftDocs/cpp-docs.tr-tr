---
title: _callnewh | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _callnewh
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _callnewh
dev_langs:
- C++
helpviewer_keywords:
- _callnewh
ms.assetid: 4dcb73e9-6384-4d12-a973-a8807d4de7a8
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cd835a404233d90193cb999b7c64bf9fb52134eb
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="callnewh"></a>_callnewh

Şu anda yüklü çağırır *yeni işleyicisi*.

## <a name="syntax"></a>Sözdizimi

```cpp
int _callnewh(
   size_t size
   )
```

### <a name="parameters"></a>Parametreler

*Boyutu*<br/>
Bellek miktarı, [new işleci](../../cpp/new-operator-cpp.md) tahsis çalışıldı.

## <a name="return-value"></a>Dönüş Değeri

|Değer|Açıklama|
|-----------|-----------------|
|0|Hata: Yeni hiçbir işleyici yüklü değil veya yeni bir işleyici etkindir.|
|1.|BAŞARI: Yeni yüklü ve etkin işleyicisidir. Bellek ayırma yeniden denenebilir.|

## <a name="exceptions"></a>Özel Durumlar

Bu işlev oluşturur [bad_alloc](../../standard-library/bad-alloc-class.md) varsa *yeni işleyicisi* bulunamıyor.

## <a name="remarks"></a>Açıklamalar

*Yeni işleyicisi* denir [new işleci](../../cpp/new-operator-cpp.md) başarıyla bellek ayırma başarısız. Yeni işleyici ardından sonraki ayırmaları başarılı bir bellek boşaltma gibi bazı uygun eylemi başlatmak.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|_callnewh|internal.h|

## <a name="see-also"></a>Ayrıca bkz.

[_set_new_handler](set-new-handler.md)<br/>
[_set_new_mode](set-new-mode.md)<br/>
