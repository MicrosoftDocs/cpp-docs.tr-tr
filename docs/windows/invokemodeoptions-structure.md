---
title: Invokemodeoptions yapısı
ms.date: 03/22/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::InvokeModeOptions
helpviewer_keywords:
- InvokeModeOptions structure
- InvokeMode enum
ms.openlocfilehash: 315f1f0c49c4222bf525bbaf25c9ad0de8b9c7d1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50511708"
---
# <a name="invokemodeoptions-structure"></a>Invokemodeoptions yapısı

Temsilci sırasındaki tüm olaylarını başlatmak için ya da bir hata oluştuktan sonra tetikleme durdurmak için belirtir. İzin verilen değerler belirtilen `InvokeMode` sabit listesi.

## <a name="syntax"></a>Sözdizimi

```cpp
enum InvokeMode
{
   StopOnFirstError = 1,
   FireAll = 2,
};

struct InvokeModeOptions
{
   static const InvokeMode invokeMode = invokeModeValue;
};
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** event.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)<br/>
[Microsoft::WRL::AgileEventSource sınıfı](../windows/agileeventsource-class.md)