---
description: 'Daha fazla bilgi edinin: ınvokemodeoptions yapısı'
title: InvokeModeOptions Yapısı
ms.date: 03/22/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::InvokeModeOptions
helpviewer_keywords:
- InvokeModeOptions structure
- InvokeMode enum
ms.openlocfilehash: 1e1382242c95c47355239c220c43c278280dd451
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298987"
---
# <a name="invokemodeoptions-structure"></a>InvokeModeOptions Yapısı

Temsilci sırasındaki tüm olayların mi tetikleneceği yoksa bir hata olduktan sonra tetiklenmesi mi durdurulacağı belirtir. İzin verilen değerler sabit listesinde belirtilir `InvokeMode` .

## <a name="syntax"></a>Syntax

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

[Microsoft:: WRL ad alanı](microsoft-wrl-namespace.md)<br/>
[Microsoft:: WRL:: AgileEventSource sınıfı](agileeventsource-class.md)
