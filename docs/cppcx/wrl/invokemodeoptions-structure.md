---
title: Invokemodeoptions yapısı
ms.date: 03/22/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::InvokeModeOptions
helpviewer_keywords:
- InvokeModeOptions structure
- InvokeMode enum
ms.openlocfilehash: 0e5b45042c9959b87ad5db97ab755e49de469149
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59035286"
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

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft::WRL Ad Alanı](microsoft-wrl-namespace.md)<br/>
[Microsoft::WRL::AgileEventSource sınıfı](agileeventsource-class.md)