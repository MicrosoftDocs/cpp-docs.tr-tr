---
title: Olay işleme genel işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlWaitWithMessageLoop
dev_langs:
- C++
helpviewer_keywords:
- event handling, global functions
- global functions, event handling
ms.assetid: fd674470-3def-47c3-be1c-894fa85f13e8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: acc8aeb54e98e531756d71d6be389dca8a494f4c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091464"
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
