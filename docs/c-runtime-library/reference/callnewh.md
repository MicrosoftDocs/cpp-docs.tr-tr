---
title: _callnewh
ms.date: 11/04/2016
api_name:
- _callnewh
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
- api-ms-win-crt-heap-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _callnewh
helpviewer_keywords:
- _callnewh
ms.assetid: 4dcb73e9-6384-4d12-a973-a8807d4de7a8
ms.openlocfilehash: 3e14450538807b164897c335f7e37d82d8562314
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70939389"
---
# <a name="_callnewh"></a>_callnewh

Şu anda yüklü olan *Yeni işleyiciyi*çağırır.

## <a name="syntax"></a>Sözdizimi

```cpp
int _callnewh(
   size_t size
   )
```

### <a name="parameters"></a>Parametreler

*boyutla*<br/>
[Yeni işlecin](../../cpp/new-operator-cpp.md) ayırmaya çalıştığı bellek miktarı.

## <a name="return-value"></a>Dönüş Değeri

|Değer|Açıklama|
|-----------|-----------------|
|0|Hataları Yeni bir işleyici yüklenmedi veya hiçbir yeni işleyici etkin değil.|
|1\.|Başarılı Yeni işleyici yüklendi ve etkin. Bellek ayırma yeniden denenebilir.|

## <a name="exceptions"></a>Özel Durumlar

Bu işlev, *yeni işleyici* bulunamıyorsa [bad_alloc](../../standard-library/bad-alloc-class.md) oluşturur.

## <a name="remarks"></a>Açıklamalar

Yeni [operatör](../../cpp/new-operator-cpp.md) belleği başarıyla ayıramazsa *yeni işleyici* çağrılır. Yeni işleyici daha sonra sonraki ayırmaların başarılı olması için belleği boşaltma gibi bazı uygun eylemleri başlatabilir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|_callnewh|iç. h|

## <a name="see-also"></a>Ayrıca bkz.

[_set_new_handler](set-new-handler.md)<br/>
[_set_new_mode](set-new-mode.md)<br/>
