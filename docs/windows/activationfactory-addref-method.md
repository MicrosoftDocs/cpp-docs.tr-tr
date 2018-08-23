---
title: ActivationFactory::AddRef yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ActivationFactory::AddRef
dev_langs:
- C++
helpviewer_keywords:
- AddRef method
ms.assetid: dfe96189-ddbe-410a-9f8d-5d8ecc8cc7e6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9b3790e0fb3d1b304359677ddedab2b65dcfe89d
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42575747"
---
# <a name="activationfactoryaddref-method"></a>ActivationFactory::AddRef Yöntemi

Geçerli başvuru sayısını artırır **ActivationFactory** nesne.

## <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD_(
   ULONG,
   AddRef
)();
```

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, hatayı açıklayan bir HRESULT.

## <a name="requirements"></a>Gereksinimler

**Başlık:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[ActivationFactory Sınıfı](../windows/activationfactory-class.md)