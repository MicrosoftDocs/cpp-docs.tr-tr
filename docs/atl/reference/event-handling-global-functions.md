---
title: Olay işleme genel işlevleri
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlWaitWithMessageLoop
helpviewer_keywords:
- event handling, global functions
- global functions, event handling
ms.assetid: fd674470-3def-47c3-be1c-894fa85f13e8
ms.openlocfilehash: 02066f2e6cd215fdb68fcdb594307b646ee69cad
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50660401"
---
# <a name="event-handling-global-functions"></a>Olay işleme genel işlevleri

Bu işlev, bir olay işleyicisi sağlar.

> [!IMPORTANT]
>  Aşağıdaki tabloda listelenen işlevi, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

|||
|-|-|
|[AtlWaitWithMessageLoop](#atlwaitwithmessageloop)|Bu arada pencere iletilerini gerektiği şekilde gönderme bildirilmesini, bir nesne için bekler.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlbase.h

##  <a name="atlwaitwithmessageloop"></a>  AtlWaitWithMessageLoop

Nesne için sinyal gönderilmesini bekler, bu arada pencere iletilerini gerektiği şekilde dağıtır.

> [!IMPORTANT]
>  Bu işlev, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

```
BOOL AtlWaitWithMessageLoop(HANDLE hEvent);
```

### <a name="parameters"></a>Parametreler

*hEvent*<br/>
[in] İşleci nesnenin bekleyin.

### <a name="return-value"></a>Dönüş Değeri

Nesne sinyal varsa TRUE değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Gerçekleşir ve gerçekleştirilecek bu bildirim bir nesnenin olay beklemek istiyor, ancak bekleme sırasında dağıtılması pencere iletilerini izin vermek yararlıdır.

## <a name="see-also"></a>Ayrıca Bkz.

[İşlevler](../../atl/reference/atl-functions.md)
