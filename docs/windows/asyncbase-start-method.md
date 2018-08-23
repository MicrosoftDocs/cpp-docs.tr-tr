---
title: AsyncBase::Start yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::Start
dev_langs:
- C++
helpviewer_keywords:
- Start method
ms.assetid: 67405c9d-0d1a-4c1e-8ea4-6ba01c1f90d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d81a3f29e99f49b03eb76f44af60c42d433e0bdc
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42611238"
---
# <a name="asyncbasestart-method"></a>AsyncBase::Start Yöntemi

Zaman uyumsuz işlemi başlatır.

## <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(
   Start
)(void);
```

## <a name="return-value"></a>Dönüş Değeri

İşlemi başlatıldığında veya zaten varsa S_OK başlatıldı; Aksi takdirde, E_ILLEGAL_STATE_CHANGE.

## <a name="remarks"></a>Açıklamalar

**Start()** varsayılan uygulamasıdır `IAsyncInfo::Start`, ve hiçbir asıl işi yapar. Aslında bir zaman uyumsuz işlemi başlatmak için geçersiz kılma `OnStart()` saf sanal yöntemi.

## <a name="requirements"></a>Gereksinimler

**Başlık:** async.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[AsyncBase Sınıfı](../windows/asyncbase-class.md)