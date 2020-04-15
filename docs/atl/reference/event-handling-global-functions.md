---
title: Olay İşleme Genel İşlevleri
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlWaitWithMessageLoop
helpviewer_keywords:
- event handling, global functions
- global functions, event handling
ms.assetid: fd674470-3def-47c3-be1c-894fa85f13e8
ms.openlocfilehash: f2f8269dcf0f59a5d0794d3f16d4c4f85d8841ac
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330144"
---
# <a name="event-handling-global-functions"></a>Olay İşleme Genel İşlevleri

Bu işlev bir olay işleyicisi sağlar.

> [!IMPORTANT]
> Aşağıdaki tabloda listelenen işlev, Windows Runtime'da çalışan uygulamalarda kullanılamaz.

|||
|-|-|
|[AtlWaitWithMessageLoop](#atlwaitwithmessageloop)|Bir nesnenin sinyal gelmesini bekler, bu arada gerektiğinde pencere iletileri gönderir.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase.h

## <a name="atlwaitwithmessageloop"></a><a name="atlwaitwithmessageloop"></a>AtlWaitWithMessageLoop

Nesne için sinyal gönderilmesini bekler, bu arada pencere iletilerini gerektiği şekilde dağıtır.

> [!IMPORTANT]
> Bu işlev, Windows Runtime'da çalışan uygulamalarda kullanılamaz.

```
BOOL AtlWaitWithMessageLoop(HANDLE hEvent);
```

### <a name="parameters"></a>Parametreler

*hOlay*<br/>
[içinde] Bekleyecek nesnenin tutamacı.

### <a name="return-value"></a>Dönüş Değeri

Nesne sinyal verilmişse TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu, bir nesnenin olayının gerçekleşmesini beklemek ve bunun gerçekleştiğinin bildirilmesini istiyorsanız, ancak beklerken pencere iletilerinin gönderilmesine izin vermek için yararlıdır.

## <a name="see-also"></a>Ayrıca bkz.

[İşlevler](../../atl/reference/atl-functions.md)
