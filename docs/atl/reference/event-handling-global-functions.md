---
title: Olay Işleme genel Işlevler
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlWaitWithMessageLoop
helpviewer_keywords:
- event handling, global functions
- global functions, event handling
ms.assetid: fd674470-3def-47c3-be1c-894fa85f13e8
ms.openlocfilehash: fde93415640ef7fa460bb363af4c3cb14b356061
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833458"
---
# <a name="event-handling-global-functions"></a>Olay Işleme genel Işlevler

Bu işlev bir olay işleyicisi sağlar.

> [!IMPORTANT]
> Aşağıdaki tabloda listelenen işlev, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

|Ad|Açıklama|
|-|-|
|[AtlWaitWithMessageLoop](#atlwaitwithmessageloop)|Bir nesne için sinyal gelmesini bekler, bu da gerektiğinde pencere iletileri gönderiyor.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="atlwaitwithmessageloop"></a><a name="atlwaitwithmessageloop"></a> AtlWaitWithMessageLoop

Nesne için sinyal gönderilmesini bekler, bu arada pencere iletilerini gerektiği şekilde dağıtır.

> [!IMPORTANT]
> Bu işlev, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

```
BOOL AtlWaitWithMessageLoop(HANDLE hEvent);
```

### <a name="parameters"></a>Parametreler

*hEvent*<br/>
'ndaki Beklenecek nesnenin tanıtıcısı.

### <a name="return-value"></a>Dönüş Değeri

Nesne sinyalliyse, doğru döndürür.

### <a name="remarks"></a>Açıklamalar

Bu, bir nesnenin olayının gerçekleşmesini beklemek ve bunun gerçekleşmekte olduğunun bildirilmesi, ancak bekleme sırasında pencere iletilerinin gönderilmesini sağlamak istiyorsanız yararlıdır.

## <a name="see-also"></a>Ayrıca bkz.

[İşlevler](../../atl/reference/atl-functions.md)
