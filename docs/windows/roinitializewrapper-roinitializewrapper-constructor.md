---
title: Roınitializewrapper::roınitializewrapper Oluşturucusu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::RoInitializeWrapper
dev_langs:
- C++
ms.assetid: c6f7fb07-14af-4574-9135-cea164607f30
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8b5cf858ae3fb3974898428b8437784ac3ce324e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46416285"
---
# <a name="roinitializewrapperroinitializewrapper-constructor"></a>RoInitializeWrapper::RoInitializeWrapper Oluşturucusu

Yeni bir örneğini başlatır **Roınitializewrapper** sınıfı.

## <a name="syntax"></a>Sözdizimi

```cpp
RoInitializeWrapper(   RO_INIT_TYPE flags)  
```

### <a name="parameters"></a>Parametreler

*bayrakları*<br/>
Windows çalışma zamanı tarafından sağlanan desteğin belirtir RO_INIT_TYPE numaralandırmalardan biri.

## <a name="remarks"></a>Açıklamalar

**Roınitializewrapper** sınıfı çağırır `Windows::Foundation::Initialize(flags)`.

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::wrl:: Wrappers

## <a name="see-also"></a>Ayrıca Bkz.

[HandleT Sınıfı](../windows/handlet-class.md)