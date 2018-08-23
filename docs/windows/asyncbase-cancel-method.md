---
title: AsyncBase::Cancel yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::Cancel
dev_langs:
- C++
helpviewer_keywords:
- Cancel method
ms.assetid: 8bfebc63-3848-4629-bc89-aa538ed7e7ad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dbf216d672dd22e453f8c213f7a9f34f08a47273
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42593143"
---
# <a name="asyncbasecancel-method"></a>AsyncBase::Cancel Yöntemi

Zaman uyumsuz bir işlem iptal eder.

## <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(
   Cancel
)(void);
```

## <a name="return-value"></a>Dönüş Değeri

Varsayılan olarak, her zaman S_OK döndürür.

## <a name="remarks"></a>Açıklamalar

**Cancel()** varsayılan uygulamasıdır `IAsyncInfo::Cancel`, ve hiçbir asıl işi yapar. Zaman uyumsuz bir işlem gerçekten iptal etmek için geçersiz kılma `OnCancel()` saf sanal yöntemi.

## <a name="requirements"></a>Gereksinimler

**Başlık:** async.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[AsyncBase Sınıfı](../windows/asyncbase-class.md)