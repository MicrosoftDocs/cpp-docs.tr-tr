---
title: _callnewh
ms.date: 4/2/2020
api_name:
- _callnewh
- _o__callnewh
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _callnewh
helpviewer_keywords:
- _callnewh
ms.assetid: 4dcb73e9-6384-4d12-a973-a8807d4de7a8
ms.openlocfilehash: d93de7f963a370810ed3b30af04d6d602abf6313
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81333660"
---
# <a name="_callnewh"></a>_callnewh

Şu anda yüklenen *yeni işleyiciyi*çağırır.

## <a name="syntax"></a>Sözdizimi

```cpp
int _callnewh(
   size_t size
   )
```

### <a name="parameters"></a>Parametreler

*Boyutu*<br/>
[Yeni işlecinin](../../cpp/new-operator-cpp.md) ayırmaya çalıştığı bellek miktarı.

## <a name="return-value"></a>Dönüş Değeri

|Değer|Açıklama|
|-----------|-----------------|
|0|Hata: Yeni işleyici yüklenmedi veya yeni işleyici etkin değil.|
|1|Başarı: Yeni işleyici yüklü ve etkin. Bellek ayırma yeniden denenebilir.|

## <a name="exceptions"></a>Özel durumlar

Yeni *işleyici* bulunamazsa, bu işlev [bad_alloc](../../standard-library/bad-alloc-class.md) atar.

## <a name="remarks"></a>Açıklamalar

[Yeni işleç](../../cpp/new-operator-cpp.md) belleği başarıyla ayıramazsa *yeni işleyici* çağrılır. Yeni işleyici daha sonra sonraki ayırmaların başarılı olması için belleği serbest leştirmek gibi bazı uygun eylemi başlatabilir.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|_callnewh|dahili.h|

## <a name="see-also"></a>Ayrıca bkz.

[_set_new_handler](set-new-handler.md)<br/>
[_set_new_mode](set-new-mode.md)<br/>
