---
title: Invokemodeoptions yapısı
ms.date: 03/22/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::InvokeModeOptions
helpviewer_keywords:
- InvokeModeOptions structure
- InvokeMode enum
ms.openlocfilehash: ff16c6c5a2ce09313283198fe0b86e95d572e46c
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54335207"
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

[Microsoft::WRL Ad Alanı](microsoft-wrl-namespace.md)<br/>
[Microsoft::WRL::AgileEventSource sınıfı](agileeventsource-class.md)