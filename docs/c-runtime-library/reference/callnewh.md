---
title: _callnewh
ms.date: 11/04/2016
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
helpviewer_keywords:
- _callnewh
ms.assetid: 4dcb73e9-6384-4d12-a973-a8807d4de7a8
ms.openlocfilehash: 98526f6c8c40b71104345563db71ef098b6cfb8d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643670"
---
# <a name="callnewh"></a>_callnewh

Şu anda yüklü çağırır *yeni işleyici*.

## <a name="syntax"></a>Sözdizimi

```cpp
int _callnewh(
   size_t size
   )
```

### <a name="parameters"></a>Parametreler

*Boyutu*<br/>
Bellek miktarı, [new işleci](../../cpp/new-operator-cpp.md) ayrılacak çalıştı.

## <a name="return-value"></a>Dönüş Değeri

|Değer|Açıklama|
|-----------|-----------------|
|0|Hata: Hiçbir yeni işleyici yüklü değil veya yok yeni işleyici etkindir.|
|1.|Başarılı: Yeni işleyici yüklü ve etkin. Bellek ayırma yeniden denenebilir.|

## <a name="exceptions"></a>Özel Durumlar

Bu işlevin [bad_alloc](../../standard-library/bad-alloc-class.md) varsa *yeni işleyici* bulunamıyor.

## <a name="remarks"></a>Açıklamalar

*Yeni işleyici* Aranan [new işleci](../../cpp/new-operator-cpp.md) başarıyla bellek ayırma başarısız olur. Yeni işleyiciyi ardından sonraki ayırma başarılı bir bellek boşaltma gibi bazı uygun eylemi başlatmak.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|_callnewh|internal.h|

## <a name="see-also"></a>Ayrıca bkz.

[_set_new_handler](set-new-handler.md)<br/>
[_set_new_mode](set-new-mode.md)<br/>
