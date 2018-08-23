---
title: Chainınterfaces::Verify yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::ChainInterfaces::Verify
dev_langs:
- C++
helpviewer_keywords:
- Verify method
ms.assetid: c591e130-8686-4130-ba69-1aaedc250038
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e6dbc595714cbecf2ad13db13051866e31e5ebcd
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42581064"
---
# <a name="chaininterfacesverify-method"></a>ChainInterfaces::Verify Yöntemi

Her arabirim şablon parametreleri tarafından tanımlanan doğrular *I0* aracılığıyla *I9* devraldığı `IUnknown` ve/veya `IInspectable`ve *I0* devralır *I1* aracılığıyla *I9*.

## <a name="syntax"></a>Sözdizimi

```cpp
WRL_NOTHROW __forceinline static void Verify();
```

## <a name="remarks"></a>Açıklamalar

Doğrulama işlemi başarısız olursa bir **static_assert** hatayı açıklayan bir hata iletisi gösterir.

Şablon parametreleri *I0* ve *I1* gereklidir ve parametreleri *I2* aracılığıyla *I9* isteğe bağlıdır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[ChainInterfaces Yapısı](../windows/chaininterfaces-structure.md)