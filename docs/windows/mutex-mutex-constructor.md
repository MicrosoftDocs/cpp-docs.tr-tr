---
title: Mutex::mutex Oluşturucusu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Mutex::Mutex
dev_langs:
- C++
helpviewer_keywords:
- Mutex, constructor
ms.assetid: 504afcdc-775a-4c98-a06f-4fb4663eba3f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 62a1fc796188c38dfbd3aff004eba15b7e30ea89
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42600511"
---
# <a name="mutexmutex-constructor"></a>Mutex::Mutex Oluşturucusu

Yeni bir örneğini başlatır **Mutex** sınıfı.

## <a name="syntax"></a>Sözdizimi

```cpp
explicit Mutex(
   HANDLE h
);

Mutex(
   _Inout_ Mutex&& h
);
```

### <a name="parameters"></a>Parametreler

*h*  
Tanıtıcı ya da bir tanıtıcı bir rvalue başvurusu için bir **Mutex** nesne.

## <a name="remarks"></a>Açıklamalar

İlk Oluşturucu başlatan bir **Mutex** nesnesinden belirtilen tanıtıcı. İkinci oluşturucu başlatan bir **Mutex** geçerli nesne belirtilen tanıtıcı, ve ardından mutex sahipliğini taşır **Mutex** nesne.

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::wrl:: Wrappers

## <a name="see-also"></a>Ayrıca Bkz.
[Mutex sınıfı](../windows/mutex-class1.md)