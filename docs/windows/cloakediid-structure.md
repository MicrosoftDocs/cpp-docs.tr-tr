---
title: CloakedIid Yapısı
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::CloakedIid
helpviewer_keywords:
- CloakedIid structure
ms.assetid: 82e0e377-ca3a-46bc-b850-ae2c46c15bb5
ms.openlocfilehash: 7340032e91a9b30b72099477b55b88740b3eb68f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50535310"
---
# <a name="cloakediid-structure"></a>CloakedIid Yapısı

Gösterir `RuntimeClass`, `Implements` ve `ChainInterfaces` şablonları belirtilen arabirim IID'si listesinde erişilebilir değil.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename T>
struct CloakedIid : T;
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
(Gizlenmiş) gizlenen arabirim.

## <a name="remarks"></a>Açıklamalar

İlişkin bir örnek verilmiştir **Cloakedıid** kullanılır: `struct MyRuntimeClass : RuntimeClass<CloakedIid<IMyCloakedInterface>> {}`.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`T`

`CloakedIid`

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)