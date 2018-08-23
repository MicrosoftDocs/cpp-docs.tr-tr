---
title: ClassFactory::LockServer yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ClassFactory::LockServer
dev_langs:
- C++
helpviewer_keywords:
- LockServer method
ms.assetid: 8d859815-956d-4f81-a5af-7cdee7e945de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5ea76974359da2002178a342ab7d9b5523c52889
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42584144"
---
# <a name="classfactorylockserver-method"></a>ClassFactory::LockServer Yöntemi

Artırır veya azaltır temel sayısını nesneleri geçerli tarafından izlenen **ClassFactory** nesne.

## <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(
   LockServer
)(BOOL fLock);
```

### <a name="parameters"></a>Parametreler

*fLock*  
**doğru** izlenen nesne sayısını artırmak için. **false** izlenen nesnelerin sayısını azaltmak için.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, E_FAIL.

## <a name="remarks"></a>Açıklamalar

**ClassFactory** temel örneği nesneleri izler [Modülü](../windows/module-class.md) sınıfı.

## <a name="requirements"></a>Gereksinimler

**Başlık:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[ClassFactory Sınıfı](../windows/classfactory-class.md)