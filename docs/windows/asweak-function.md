---
title: AsWeak işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::AsWeak
dev_langs:
- C++
helpviewer_keywords:
- AsWeak function
ms.assetid: a6f10cfc-c1d6-4761-adb9-1a119cc99913
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dea10165e920c6b0bbd3856fc04e9ec9661e60c4
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42571340"
---
# <a name="asweak-function"></a>AsWeak İşlevi

Belirtilen bir örneğe zayıf bir başvuru alır.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename T>
HRESULT AsWeak(
   _In_ T* p,
   _Out_ WeakRef* pWeak
);
```

### <a name="parameters"></a>Parametreler

*T*  
Parametresinin türü için bir işaretçi *p*.

*p*  
Bir tür örneği.

*pWeak*  
Bu işlem tamamlandığında, zayıf bir başvuru parametresi için bir işaretçiye *p*.

## <a name="return-value"></a>Dönüş Değeri

Bu işlem başarılı olursa S_OK; Aksi takdirde, hatanın nedenini gösteren HRESULT hatası.

## <a name="requirements"></a>Gereksinimler

**Başlık:** client.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)