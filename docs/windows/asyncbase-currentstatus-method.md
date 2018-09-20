---
title: AsyncBase::CurrentStatus yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::CurrentStatus
dev_langs:
- C++
helpviewer_keywords:
- CurrentStatus method
ms.assetid: 26ee4c4a-6525-4a5f-b49c-3ca40c365eb6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 792f9f6c6d76097459498c43068f46d86b2e2349
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46401491"
---
# <a name="asyncbasecurrentstatus-method"></a>AsyncBase::CurrentStatus Yöntemi

Geçerli zaman uyumsuz işlemin durumunu alır.

## <a name="syntax"></a>Sözdizimi

```cpp
inline void CurrentStatus(
   Details::AsyncStatusInternal *status
);
```

### <a name="parameters"></a>Parametreler

*Durumu*<br/>
Bu işlem geçerli durumu depoladığı konum.

## <a name="remarks"></a>Açıklamalar

Bu işlem, iş parçacığı açısından güvenlidir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** async.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[AsyncBase Sınıfı](../windows/asyncbase-class.md)<br/>
[AsyncStatusInternal Sabit Listesi](../windows/asyncstatusinternal-enumeration.md)