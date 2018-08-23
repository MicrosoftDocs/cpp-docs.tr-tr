---
title: WeakRef::WeakRef Oluşturucusu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef::WeakRef
dev_langs:
- C++
helpviewer_keywords:
- WeakRef, constructor
ms.assetid: 589f87e0-8dcc-4e82-aab2-f2f66f1ec47c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d7c8bc81040ce8d4c1cea7497f9d1371fbb9d41f
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42611616"
---
# <a name="weakrefweakref-constructor"></a>WeakRef::WeakRef Oluşturucusu

Yeni bir örneğini başlatır **WeakRef** sınıfı.

## <a name="syntax"></a>Sözdizimi

```cpp
WeakRef();
WeakRef(
   decltype(__nullptr)  
);

WeakRef(
   _In_opt_ IWeakReference* ptr
);

WeakRef(
   const ComPtr<IWeakReference>& ptr
);

WeakRef(
   const WeakRef& ptr
);

WeakRef(
   _Inout_ WeakRef&& ptr
);
```

### <a name="parameters"></a>Parametreler

*ptr*  
Bir işaretçi, başvuru veya rvalue başvurusunu geçerli başlatır, varolan bir nesneye **WeakRef** nesne.

## <a name="remarks"></a>Açıklamalar

İlk Oluşturucu boş bir başlatır **WeakRef** nesne. İkinci oluşturucu başlatan bir **WeakRef** işaretçisi nesneden `IWeakReference` arabirimi. Üçüncü Oluşturucu başlatan bir **WeakRef** başvuru nesneden bir `ComPtr<IWeakReference>` nesne. Dördüncü ve beşinci oluşturucular başlatan bir **WeakRef** başka bir nesne **WeakRef** nesne.

## <a name="requirements"></a>Gereksinimler

**Başlık:** client.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[WeakRef Sınıfı](../windows/weakref-class.md)