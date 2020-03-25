---
title: Invokemodeoptions yapısı
ms.date: 03/22/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::InvokeModeOptions
helpviewer_keywords:
- InvokeModeOptions structure
- InvokeMode enum
ms.openlocfilehash: 9bca49479d97ee371f6728f90a9aa96da0387f54
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213843"
---
# <a name="invokemodeoptions-structure"></a>Invokemodeoptions yapısı

Temsilci sırasındaki tüm olayların mi tetikleneceği yoksa bir hata olduktan sonra tetiklenmesi mi durdurulacağı belirtir. `InvokeMode` numaralandırmasında izin verilen değerler belirtilmiştir.

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

**Üstbilgi:** Event. h

**Ad alanı:** Microsoft:: WRL

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft::WRL Ad Alanı](microsoft-wrl-namespace.md)<br/>
[Microsoft:: WRL:: AgileEventSource sınıfı](agileeventsource-class.md)
